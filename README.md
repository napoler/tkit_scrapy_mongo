# tkit_scrapy_mongo
use mongodb instead of redis and rewrite scrapy_redis py3 module


```

    # 这里覆盖默认的settings配置,custom_settings settings.py
    custom_settings = dict(
        #MONGODB_URI="mongodb://192.168.1.18:27017/",
        #REDIS_URL = 'redis://192.168.1.18:6379',  # 指定redis的地址
        #POOL_PROXY = "http://192.168.1.18:5010"
        CONCURRENT_REQUESTS_PER_IP = 4,
        CONCURRENT_REQUESTS_PER_DOMAIN = 4,
        DUPEFILTER_CLASS = 'pet.tkit_scrapy_mongo.dupefilter.RFPDupeFilter',
        # 去重复
        SPIDER_MIDDLEWARES={
            # "scrapy_splash.SplashDeduplicateArgsMiddleware": 100,
            "pet.tkit_scrapy_mongo.dupefilter.RFPDupeFilter":101
        }


    )


```


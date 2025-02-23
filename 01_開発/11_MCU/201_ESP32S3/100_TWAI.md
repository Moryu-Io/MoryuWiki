## TWAI memo


```
build_flags = 
  -DCONFIG_TWAI_ISR_IN_IRAM=1

```

```
g_config.intr_flags = ESP_INTR_FLAG_IRAM
```

https://docs.espressif.com/projects/esp-idf/en/v5.2.4/esp32s3/api-reference/kconfig.html#component-config-driver-configurations-twai-configuration

https://esp32.com/viewtopic.php?f=12&t=43172
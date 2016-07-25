# SSL Certificate Information API

This repository provides a web service for accessing SSL Certificate information.

## Usage

To run the project locally:

    php -S 0.0.0.0:8080 -t public public/index.php

This project also supports being deployed to Heroku.

## Documentation

The API returns exclusively JSON and follows the [JSON API](http://jsonapi.org/) conventions.

### GET /certificate/{domain}

#### 200 OK

    {
      "data": [
        {
          "type": "certificate",
          "id": "github.com",
          "attributes": {
            "name": "\/businessCategory=Private Organization\/1.3.6.1.4.1.311.60.2.1.3=US\/1.3.6.1.4.1.311.60.2.1.2=Delaware\/serialNumber=5157550\/street=88 Colin P Kelly, Jr Street\/postalCode=94107\/C=US\/ST=California\/L=San Francisco\/O=GitHub, Inc.\/CN=github.com",
            "validFrom": "Thu, 10 Mar 2016 00:00:00 +0000",
            "validTo": "Thu, 17 May 2018 12:00:00 +0000",
            "subject": {
              "businessCategory": "Private Organization",
              "UNDEF": [
                "US",
                "Delaware"
              ],
              "serialNumber": "5157550",
              "street": "88 Colin P Kelly, Jr Street",
              "postalCode": "94107",
              "C": "US",
              "ST": "California",
              "L": "San Francisco",
              "O": "GitHub, Inc.",
              "CN": "github.com"
            },
            "issuer": {
              "C": "US",
              "O": "DigiCert Inc",
              "OU": "www.digicert.com",
              "CN": "DigiCert SHA2 Extended Validation Server CA"
            },
            "sans": [
              "github.com",
              "www.github.com"
            ],
            "cert": "-----BEGIN CERTIFICATE-----\nMIIHeTCCBmGgAwIBAgIQC\/20CQrXteZAwwsWyVKaJzANBgkqhkiG9w0BAQsFADB1\nMQswCQYDVQQGEwJVUzEVMBMGA1UEChMMRGlnaUNlcnQgSW5jMRkwFwYDVQQLExB3\nd3cuZGlnaWNlcnQuY29tMTQwMgYDVQQDEytEaWdpQ2VydCBTSEEyIEV4dGVuZGVk\nIFZhbGlkYXRpb24gU2VydmVyIENBMB4XDTE2MDMxMDAwMDAwMFoXDTE4MDUxNzEy\nMDAwMFowgf0xHTAbBgNVBA8MFFByaXZhdGUgT3JnYW5pemF0aW9uMRMwEQYLKwYB\nBAGCNzwCAQMTAlVTMRkwFwYLKwYBBAGCNzwCAQITCERlbGF3YXJlMRAwDgYDVQQF\nEwc1MTU3NTUwMSQwIgYDVQQJExs4OCBDb2xpbiBQIEtlbGx5LCBKciBTdHJlZXQx\nDjAMBgNVBBETBTk0MTA3MQswCQYDVQQGEwJVUzETMBEGA1UECBMKQ2FsaWZvcm5p\nYTEWMBQGA1UEBxMNU2FuIEZyYW5jaXNjbzEVMBMGA1UEChMMR2l0SHViLCBJbmMu\nMRMwEQYDVQQDEwpnaXRodWIuY29tMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIB\nCgKCAQEA54hc8pZclxgcupjiA\/F\/OZGRwm\/ZlucoQGTNTKmBEgNsrn\/mxhngWmPw\nbAvUaLP\/\/T79Jc+1WXMpxMiz9PK6yZRRFuIo0d2bx423NA6hOL2RTtbnfs+y0PFS\n\/YTpQSelTuq+Fuwts5v6aAweNyMcYD0HBybkkdosFoDccBNzJ92Ac8I5EVDUc3Or\n\/4jSyZwzxu9kdmBlBzeHMvsqdH8SX9mNahXtXxRpwZnBiUjw36PgN+s9GLWGrafd\n02T0ux9Yzd5ezkMxukqEAQ7AKIIijvaWPAJbK\/52XLhIy2vpGNylyni\/DQD18bBP\nT+ZG1uv0QQP9LuY\/joO+FKDOTler4wIDAQABo4IDejCCA3YwHwYDVR0jBBgwFoAU\nPdNQpdagre7zSmAKZdMh1Pj41g8wHQYDVR0OBBYEFIhcSGcZzKB2WS0RecO+oqyH\nIidbMCUGA1UdEQQeMByCCmdpdGh1Yi5jb22CDnd3dy5naXRodWIuY29tMA4GA1Ud\nDwEB\/wQEAwIFoDAdBgNVHSUEFjAUBggrBgEFBQcDAQYIKwYBBQUHAwIwdQYDVR0f\nBG4wbDA0oDKgMIYuaHR0cDovL2NybDMuZGlnaWNlcnQuY29tL3NoYTItZXYtc2Vy\ndmVyLWcxLmNybDA0oDKgMIYuaHR0cDovL2NybDQuZGlnaWNlcnQuY29tL3NoYTIt\nZXYtc2VydmVyLWcxLmNybDBLBgNVHSAERDBCMDcGCWCGSAGG\/WwCATAqMCgGCCsG\nAQUFBwIBFhxodHRwczovL3d3dy5kaWdpY2VydC5jb20vQ1BTMAcGBWeBDAEBMIGI\nBggrBgEFBQcBAQR8MHowJAYIKwYBBQUHMAGGGGh0dHA6Ly9vY3NwLmRpZ2ljZXJ0\nLmNvbTBSBggrBgEFBQcwAoZGaHR0cDovL2NhY2VydHMuZGlnaWNlcnQuY29tL0Rp\nZ2lDZXJ0U0hBMkV4dGVuZGVkVmFsaWRhdGlvblNlcnZlckNBLmNydDAMBgNVHRMB\nAf8EAjAAMIIBfwYKKwYBBAHWeQIEAgSCAW8EggFrAWkAdgCkuQmQtBhYFIe7E6LM\nZ3AKPDWYBPkb37jjd80OyA3cEAAAAVNhieoeAAAEAwBHMEUCIQCHHSEY\/ROK2\/sO\nljbKaNEcKWz6BxHJNPOtjSyuVnSn4QIgJ6RqvYbSX1vKLeX7vpnOfCAfS2Y8lB5R\nNMwk6us2QiAAdgBo9pj4H2SCvjqM7rkoHUz8cVFdZ5PURNEKZ6y7T0\/7xAAAAVNh\niennAAAEAwBHMEUCIQDZpd5S+3to8k7lcDeWBhiJASiYTk2rNAT26lVaM3xhWwIg\nNUqrkIODZpRg+khhp8ag65B8mu0p4JUAmkRDbiYnRvYAdwBWFAaaL9fC7NP14b1E\nsj7HRna5vJkRXMDvlJhV1onQ3QAAAVNhieqZAAAEAwBIMEYCIQDnm3WStlvE99GC\nizSx+UGtGmQk2WTokoPgo1hfiv8zIAIhAPrYeXrBgseA9jUWWoB4IvmcZtshjXso\nnT8MIG1u1zF8MA0GCSqGSIb3DQEBCwUAA4IBAQCLbNtkxuspqycq8h1EpbmAX0wM\n5DoW7hM\/FVdz4LJ3Kmftyk1yd8j\/PSxRrAQN2Mr\/frKeK8NE1cMji32mJbBqpWtK\n\/+wC+avPplBUbNpzP53cuTMF\/QssxItPGNP5\/OT9Aj1BxA\/NofWZKh4ufV7cz3pY\nRDS4BF+EEFQ4l5GY+yp4WJA\/xSvYsTHWeWxRD1\/nl62\/Rd9FN2NkacRVozCxRVle\nFrBHTFxqIP6kDnxiLElBrZngtY07ietaYZVLQN\/ETyqLQftsf8TecwTklbjvm8NT\nJqbaIVifYwqwNN+4lRxS3F5lNlA\/il12IOgbRioLI62o8G0DaEUQgHNf8vSG\n-----END CERTIFICATE-----\n"
          }
        }
      ],
      "errors": [

      ]
    }

#### 500 Internal Server Error

    {
      "data": [

      ],
      "errors": [
        {
          "code": 2001,
          "title": "Unable to extract data from certificate."
        }
      ]
    }
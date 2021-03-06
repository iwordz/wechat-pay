.. wechat-pay-sdk documentation master file, created by
   sphinx-quickstart on Tue Dec 19 18:32:24 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to wechat-pay-sdk's documentation!
******************************************

   wechat-pay-sdk is an unofficial sdk for WeChat pay. It contains almost all API of WeChat pay.

   Code host at `Github <https://github.com/Narcissist1/wechat-pay>`_

Install WeChat-Pay-SDK
======================
   Install with **pip**:

       ``pip install wechat-pay-sdk``

   Or

   Install from source

       ``python setup.py install``


How To Use
==========

   Import the WeChatPay class and init it with your own parameters::

        from wechatpay import WeChatPay

        WECHAT_APPID = 'your_app_id'
        WECHAT_MCH_ID = 'your_mch_id'
        WECHAT_NOTIFY_URL = 'your_notify_url'
        WECHAT_PAY_SECRET = 'your_pay_secret'
        WECHAT_CERT = 'path/to/your_cert.pem'
        WECHAT_KEY = 'patch/to/your_key.pem'


        sp = WeChatPay(WECHAT_APPID, WECHAT_MCH_ID,
                           WECHAT_NOTIFY_URL, WECHAT_PAY_SECRET, WECHAT_CERT, WECHAT_KEY)

        # post order
        result = sp.unifiedorder(body=body, out_trade_no=out_trade_no, total_fee=total_fee,
                                     spbill_create_ip=client_ip)

        # order query
        result = sp.query_order(out_trade_no=out_trade_no)


        # download bills
        result = sp.downloadbill(bill_date=bill_date, bill_type=bill_type)

        # refund (this method need your cert.pem and key.pem file which need you to download from the official website)
        result = sp.refund(out_trade_no, out_refund_no, total_fee, total_fee)

        # refund query
        result = sp.refund_query(out_trade_no)

        if result.success:
            # your code
            pass

API
===
.. toctree::
   :maxdepth: 2

   WeChatPay
   WeChatResult

Indices and tables
==================

* :ref:`genindex`
* :ref:`search`

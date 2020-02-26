image_app
=========

Documentation
-------------
生成文字图片：在一定的区域，支持换行，丢弃，缩小来完成适应区域
The documentation is hosted at https://github.com/BingerYang/image_app


Installation
------------

.. code:: shell

     pip install image_app

Usage
-----

example:
在一张图中找到连续相似的一片片长方向区域

::

    # -*- coding: utf-8 -*-
    import os
    from image_app import load_smooth_area
    import cv2
    path = os.path.abspath("1.jpg")
    image = cv2.imread(path)
    rects = load_smooth_area(image)
    for rect in rects:
        cv2.rectangle(image, (rect[0], rect[1]), (rect[2], rect[3]), (120, 78, 255), 2)
    cv2.imwrite('test.jpg', image)
    cv2.imshow("test", image)
    cv2.waitKey(3000)



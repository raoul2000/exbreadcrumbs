![EXBreadcrumbs](http://s172418307.onlinehome.fr/project/yiiDemo/images/exbreadcrumbs.png "EXBreadcrumbs")

This extension is a wrapper for the [XBreadcrumb JQuery plugin](http://www.ajaxblender.com/xbreadcrumbs.html "XBreadcrumb JQuery plugin"). **It is compatible with the core CBreadcrumbs widget**, so no change is needed if you want to turn your old breadcrumbs into super cool extended ones.

**Check out the [demo ](http://s172418307.onlinehome.fr/project/yiiDemo/index.php?r=extension/exbreadcrumbs "demo")!**

##Requirements

tested with Yii 1.1.3 (but I see no reason why it would not work for previous Yii versions)

##Installation

1. Download and unzip the archive into your protected/extension folder
2. ...there is nothing else to do !

##Usage

To turn your default breadcrumbs into super cool extended breadcrumbs, just replace the reference to 'zii.widgets.CBreadcrumbs' by 'application.extensions.exbreadcrumbs.ExBreadcrumbs', which should be located in your main layout (protected/views/layout/main.php).

~~~
[php]
<?php 
	$this->widget('application.extensions.exbreadcrumbs.EXBreadcrumbs', array(
		'links'=>$this->breadcrumbs,
	)); 
?>
~~~

But (hopefully) there's more :

- add a dropdown menu to all (or some) breadcrumbs
- make your breadcrumbs 'collapsible'
- define your own custom style

Below is an example where the _crumb1_ has a dropdown menu containing 2 links. The link associated with _crumb2_ is defined as a classical Yii url array and at last, the _yii_ crumb url is a simple string.

~~~
[php]
$this->widget('application.extensions.exbreadcrumbs.EXBreadcrumbs', array(
    'links'=>array(
        'crumb1' => array('controller/route1','param1'=>'value1',
            'menu'=>array(
                'menu1'=> array('controller/routeMenu1','paramM1' => 'valueM1'),
                'menu2'=> array('controller/routeMenu2','paramM2' => 'valueM2'),
            )
        ),    
        'crumb2' => array('controller/route2','param2'=>'value2'),
        'yii' => 'http://www.yiiframework.com/',
        'end'
    ),
));
~~~

##Changes

**version 1.0.0.1** 

- change Client script registration to be compatible with previous Yii version (trejder)


**version 1.0.0.0** 

- initial release

##Resources
 * [forum discussion](http://www.yiiframework.com/forum/index.php?/topic/24730-extension-exbreadcrumbs/page__view__findpost__p__119734)
 * [Try out a demo](http://s172418307.onlinehome.fr/project/yiiDemo/index.php?r=extension/exbreadcrumbs)

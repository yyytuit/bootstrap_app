# bootstrap テンプレート導入手順

## gemを入れる

今回使ったGemファイル

```rb
gem 'bootstrap-sass'
gem 'jquery-rails'
gem 'font-awesome-rails'
```
font-awesome-rails以外は必ず入れる

font-awesome-railsはfont-awesome.min.cssファイイルを使う場合のみ必要。

その後bundle installする

```
 $ bundle install
```


## ファイルを移動する
テンプレートファイルをダウンロードする。

ダウンロードしたファイルを確認し、それぞれのファイルをいかに入れる。

* app/assets/javascripts下に.jsファイルを入れる

今回入れたjsファイル

```
app/assets/javascripts/bootstrap.js
app/assets/javascripts/contact.js
app/assets/javascripts/html5.js
app/assets/javascripts/jquery-2.1.3.min.js
app/assets/javascripts/jquery-migrate-1.2.1.min.js
app/assets/javascripts/jquery.actual.min.js
app/assets/javascripts/jquery.scrollTo.min.js
app/assets/javascripts/respond.js
app/assets/javascripts/script.js
app/assets/javascripts/selectivizr.js
app/assets/javascripts/smoothscroll.js
```

* app/assets/stylesheets下に.cssファイルを入れる

今回入れたcssファイル

```
app/assets/stylesheets/bootstrap.min.css
app/assets/stylesheets/font-awesome.min.css
app/assets/stylesheets/style.css
```

また画像はpublic下にimagesフォルダを作り、その中に入れる。

なぜassets下ではなくpublic下なのかという理由は[こちら](https://qiita.com/wadako111/items/03bc00d914e62243a511)を参考。

## app/assets/stylesheets/application.scssに変更
app/assets/stylesheets/application.cssの拡張子をscssに変更

また以下をapplication.scssに記述

```scss
 @import "bootstrap-sprockets";
 @import "bootstrap";
 @import "font-awesome";
```

ちなみにfont-awesome以外は必ず入れる。


## index.htmlの内容を任意のファイルに記述
ダウンロードしたファイルの中におそらくindex.html.erbがあると思います。

もしくは自分が使いたいhtmlファイルを使用します。

まずは、適当なルーティングとコントローラーとerbファイルを用意します。

* routing
```rb
Rails.application.routes.draw do
  get 'pages/index'
end
```

* app/controllers/pages_controller.rb
```rb
class PagesController < ApplicationController
  def index
  end
end
```

* app/views/pages/index.html.erb

また全てのファイルが用意できたら、erbファイルに使用するhtmlファイルをコピペしましょう。

ちなみに以下のhtmlは途中省略しています。

```html
<!DOCTYPE html>
<!--[if IE 7 ]><html class="ie ie7 lte9 lte8 lte7" lang="en-US"><![endif]-->
<!--[if IE 8]><html class="ie ie8 lte9 lte8" lang="en-US">	<![endif]-->
<!--[if IE 9]><html class="ie ie9 lte9" lang="en-US"><![endif]-->
<!--[if (gt IE 9)|!(IE)]><!-->
<html class="noIE" lang="en-US">
<!--<![endif]-->
	<head>
		<title>Nevada Plus</title>

		<!-- meta -->
		<meta http-equiv="X-UA-Compatible" content="IE=edge">
		<meta http-equiv="Content-Type" content="text/html; charset=UTF-8"/>
		<meta name="viewport" content="width=device-width, initial-scale = 1.0, maximum-scale=1.0, user-scalable=no"/>
		
		<!-- google fonts -->
		<link href='http://fonts.googleapis.com/css?family=Raleway:500,300' rel='stylesheet' type='text/css'>
		<link rel='stylesheet' href='http://fonts.googleapis.com/css?family=PT+Sans'>
		<link href='http://fonts.googleapis.com/css?family=Open+Sans' rel='stylesheet' type='text/css'>
		<link rel="stylesheet" href="http://fonts.googleapis.com/css?family=Droid+Serif:regular,bold"/>
		
		<!-- css -->
		<link rel="stylesheet" href="assets/css/bootstrap.min.css">
		<link rel="stylesheet" href="assets/css/font-awesome.min.css">
		<link rel="stylesheet" href="assets/css/style.css" media="screen"/>

		<!-- HTML5 shim and Respond.js IE8 support of HTML5 elements and media queries -->
		<!--[if lt IE 9]>
			<script src="assets/js/html5shiv.js"></script>
			<script src="assets/js/respond.js"></script>
		<![endif]-->

		<!--[if IE 8]>
	    	<script src="assets/js/selectivizr.js"></script>
	    <![endif]-->
	</head>
	
	<body>
		<header class="top-header">
			<div class="container">
				<div class="row">
					<div class="col-md-3 col-xs-5 col-sm-4 header-logo">
						<br>
						<a href="index.html"> 
							<h1 class="logo">Nevada <span class="logo-head">Plus</span></h1>
						</a>
					</div>

					<div class="col-md-8 col-md-offset-1 col-xs-7">
						<nav class="navbar navbar-default">
						  	<div class="container-fluid nav-bar">
						    <!-- Brand and toggle get grouped for better mobile display -->
							    <div class="navbar-header">
							      	<button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1">
								        <span class="sr-only">Toggle navigation</span>
								        <span class="icon-bar"></span>
								        <span class="icon-bar"></span>
								        <span class="icon-bar"></span>
							      	</button>
							    </div>

						    	<!-- Collect the nav links, forms, and other content for toggling -->
							    <div class="collapse navbar-collapse navbar-def" id="bs-example-navbar-collapse-1">
							      
							      	<ul class="nav navbar-nav navbar-right">
							        	<li>
											<a href="#wrapper"><i class="fa fa-home"></i> Home</a>
										</li>
										<li>
											<a href="#about"><i class="fa fa-bookmark"></i> About</a>
										</li>
										<li>
											<a href="#portfolio"><i class="fa fa-bookmark"></i> Portfolio</a>
										</li>
										<li>
											<a href="#services"><i class="fa fa-tasks"></i> Service</a>
										</li>
										<li>
											<a href="#blog"><i class="fa fa-wordpress"></i> Blog</a>
										</li>
										<li>
											<a href="#testimonials"><i class="fa fa-thumbs-up"></i> Testimonial</a>
										</li>
							      	</ul>
							    </div><!-- /navbar-collapse -->
						  	</div><!-- / .container-fluid -->
						</nav>
					</div>
				</div>
			</div>
		</header>

		<div id="wrapper">
			
			<div id="header" class="content-block">
				<!-- <section class="top clearfix">
					<div class="pull-left">
						<h1><a class="logo" href="index.html">Nevada <span class="logo-head">Plus</span></a></h1>
					</div>
					<! <div class="pull-right">
						<a class="toggleDrawer" href="#"><i class="fa fa-bars fa-2x"></i></a>
					</div> 
				</section>-->
				<section class="center">
					<div class="slogan">
						SLIM &amp; STYLISH
					</div>
					<div class="secondary-slogan">
						The Nevada plus Theme By ThemeWagon.
					</div>
				</section>
			</div><!-- header -->

			一部省略

			<div class="content-block" id="footer">
				<div class="container">
					<div class="row">
							<div class="col-sm-4 blog-post">
								
								<h2 class="footer-block">Have a question</h2>
								<p>Praesent lacinia dapibus, accumsan vesti bulum. Pellen tesque molestie mollis.</p>

								<p>Mauris nec ligula dui, fermentum nisl ut magna dolor, rhoncus wisi. In lacus sagittis luctus, nisl eros, sit amet tempor et, accumsan eget, pede. Suspendisse est. Ut rhoncus eu, pede. Vestibulum ante ipsum dolor lorem, iaculis mi. Pellentesque eu urna eget dolor. Duis luctus a, dolor. Duis ac sapien. 
								</p>

								<p>Estibulum dapibus, maurimalesfames ac turpis velit, rhoncus eu, luctus et interdum adipiscing wisi. Aliquam erat ac ipsum. Integer aliquam purus ultricies gravida vitae...</p>
							</div>
							<div class="col-sm-4 blog-post">
								<h2 class="footer-block">Leave us a message</h2>
								<form action="contact-form.php" id="contactForm" method="post" name="contactform" class="" role="form">
									<div class="form-group">
								    	<input type="text" class="form-control form-control-white" id="name" name="name" placeholder="Your Name" required>
								  	</div>
								    <div class="form-group">
								    	<input type="email" class="form-control form-control-white" id="email" name="email" placeholder="Enter email" required>
								    </div>
								    <div class="form-group">
								    	<textarea class="form-control form-control-white" id="message" name="massage" placeholder="Write Something" required></textarea>
								    </div>
								    <div id="contactFormResponse"></div>
								    <div class="form-group">
								    	<input id="cfsubmit" type="submit" class="text-center btn btn-o-white" value="Say Hello">
								  	</div>
								</form>
							</div>
							<div class="col-sm-4 blog-post">
								
								<h2 class="footer-block">Contact Details</h2>
								<ul>
									<li class="address-sub"><i class="fa fa-map-marker"></i>Office Address</li>
										<p>
											Blabla Parkway, P.o Box 353 Mountain View. United States of America. 
										</p>
									<li class="address-sub"><i class="fa fa-phone"></i>Phone</li>
										<p>
											Local: 1-800-123-hello<br>
											Mobile: 1-800-123-hello
										</p>
									<li class="address-sub"><i class="fa fa-envelope-o"></i>Email Address</li>
										<p>
											<a href="mailto:info@themewagon.com">info@themewagon.com</a><br>
											<a href="http://www.themewagon.com/">www.themewagon.com</a>
										</p>


								</ul>
								<div class="social">
									<a href="#"><i class="fa fa-twitter"></i></a>
									<a href="#"><i class="fa fa-facebook"></i></a>
									<a href="#"><i class="fa fa-instagram"></i></a>
									<a href="#"><i class="fa fa-pinterest-p"></i></a>
									<a href="#"><i class="fa fa-google-plus"></i></a>
									<a href="#"><i class="fa fa-skype"></i></a>
								</div>
								
							</div>
						</div>
				</div>
			</div>
			<div class="content-block footer-bottom" id="footer">
				<div class="container">
					<div class="row">
						<div class="col-xs-6">&copy; Copyright Nevada Plus 2015</div>
						<div class="col-xs-6 text-right">Theme by <a href="http://www.themewagon.com/" target="_blink">ThemeWagon</a></div>
					</div>
				</div>
			</div><!-- #footer -->

		</div><!--/#wrapper-->




		<script src="assets/js/jquery-2.1.3.min.js"></script>
		<script src="assets/js/bootstrap.js"></script>
		<script src="assets/js/jquery.actual.min.js"></script>
		<script src="assets/js/jquery.scrollTo.min.js"></script>
		<script src="assets/js/contact.js"></script>
		<script src="assets/js/script.js"></script>
		<script src="assets/js/smoothscroll.js"></script>
		<script type="text/javascript">
		jQuery(document).ready(function($){

		  	$(window).scroll(function() {
		  		
		  		console.log("asdf");

				if ($(window).scrollTop() > 100 ){
		    
		 		$('.top-header').addClass('shows');
		    
		  		} else {
		    
		   	 	$('.top-header').removeClass('shows');
		    
		 		};   	
			});

		  });

		jQuery('.scroll').on('click', function(e){		
				e.preventDefault()
		    
		  jQuery('html, body').animate({
		      scrollTop : jQuery(this.hash).offset().top
		    }, 1500);
		});


		</script>


	</body>
</html>
```

貼り終わったら一度動作確認をしてください。

```
$ rails s
```

ルーティングで設定したパス(今回は/pages/index)を開いてみましょう。

そうするとある程度体裁が整った画面がでるはずです。

ちなみにこの状態では写真がうまく表示されていないはずです。

また写真意外にも画面に大きく崩れがある場合や、jsが動かないなどする場合は、今までの手順をもう一度見直してください。


## 画像の部分でパスを変更

コピペしたindex.htmlの画像と、cssのバックグランドで設定している画像が表示されていないと思います。

現状は以下のような画像ファイルのパスを呼び出していると思います。

まずはindex.htmlとcssファイルの中からassets/imagesなどのパスで呼び出している画像ファイルをさがしてください。

例
```
assets/images/01_200x200.png
```

これを全て

```
/images/01_200x200.png
```

に変更してください。

もう一度サーバーを起動すると綺麗に画像も表示されるはずです。

## 最後にindex.htmlの整理

erbに丸ごとコピペしたhtmlファイルの一部をapplication.html.erbに移植しましょう。

そうすることで、全体ページに反映されます。

```html
<!DOCTYPE html>
<!--[if IE 7 ]><html class="ie ie7 lte9 lte8 lte7" lang="en-US"><![endif]-->
<!--[if IE 8]><html class="ie ie8 lte9 lte8" lang="en-US">	<![endif]-->
<!--[if IE 9]><html class="ie ie9 lte9" lang="en-US"><![endif]-->
<!--[if (gt IE 9)|!(IE)]><!-->
<html class="noIE" lang="en-US">
<!--<![endif]-->
	<head>
		<title>Nevada Plus</title>

		<!-- meta -->
		<meta http-equiv="X-UA-Compatible" content="IE=edge">
		<meta http-equiv="Content-Type" content="text/html; charset=UTF-8"/>
		<meta name="viewport" content="width=device-width, initial-scale = 1.0, maximum-scale=1.0, user-scalable=no"/>
		
		<!-- google fonts -->
		<link href='http://fonts.googleapis.com/css?family=Raleway:500,300' rel='stylesheet' type='text/css'>
		<link rel='stylesheet' href='http://fonts.googleapis.com/css?family=PT+Sans'>
		<link href='http://fonts.googleapis.com/css?family=Open+Sans' rel='stylesheet' type='text/css'>
		<link rel="stylesheet" href="http://fonts.googleapis.com/css?family=Droid+Serif:regular,bold"/>
		
		<!-- css -->
		<link rel="stylesheet" href="assets/css/bootstrap.min.css">
		<link rel="stylesheet" href="assets/css/font-awesome.min.css">
		<link rel="stylesheet" href="assets/css/style.css" media="screen"/>

		<!-- HTML5 shim and Respond.js IE8 support of HTML5 elements and media queries -->
		<!--[if lt IE 9]>
			<script src="assets/js/html5shiv.js"></script>
			<script src="assets/js/respond.js"></script>
		<![endif]-->

		<!--[if IE 8]>
	    	<script src="assets/js/selectivizr.js"></script>
	    <![endif]-->
	</head>
	<body>

  <script src="assets/js/jquery-2.1.3.min.js"></script>
		<script src="assets/js/bootstrap.js"></script>
		<script src="assets/js/jquery.actual.min.js"></script>
		<script src="assets/js/jquery.scrollTo.min.js"></script>
		<script src="assets/js/contact.js"></script>
		<script src="assets/js/script.js"></script>
		<script src="assets/js/smoothscroll.js"></script>
		<script type="text/javascript">
		jQuery(document).ready(function($){

		  	$(window).scroll(function() {
		  		
		  		console.log("asdf");

				if ($(window).scrollTop() > 100 ){
		    
		 		$('.top-header').addClass('shows');
		    
		  		} else {
		    
		   	 	$('.top-header').removeClass('shows');
		    
		 		};   	
			});

		  });

		jQuery('.scroll').on('click', function(e){		
				e.preventDefault()
		    
		  jQuery('html, body').animate({
		      scrollTop : jQuery(this.hash).offset().top
		    }, 1500);
		});


		</script>
  </body>
</html>
```
head内に関しては上記の中からmetaとgoogle fontsは移植します。

また以下ファイルはapp/assets/stylesheetsとapp/assets/javascripts内に全て保存し、

application.html.erb内の以下コードで呼び出されているので移植は不要です。

```
   <%= stylesheet_link_tag    'application', media: 'all', 'data-turbolinks-track': 'reload' %>
   <%= javascript_include_tag 'application', 'data-turbolinks-track': 'reload' %>
```

```html
<!-- css -->
		<link rel="stylesheet" href="assets/css/bootstrap.min.css">
		<link rel="stylesheet" href="assets/css/font-awesome.min.css">
		<link rel="stylesheet" href="assets/css/style.css" media="screen"/>
    <script src="assets/js/jquery-2.1.3.min.js"></script>


一部省略

<!-- js -->
		<script src="assets/js/bootstrap.js"></script>
		<script src="assets/js/jquery.actual.min.js"></script>
		<script src="assets/js/jquery.scrollTo.min.js"></script>
		<script src="assets/js/contact.js"></script>
		<script src="assets/js/script.js"></script>
		<script src="assets/js/smoothscroll.js"></script>
```

また以下のコードはjsファイルが用意されていないので、application.html.ebに移植しました。

```html
<script type="text/javascript">
  jQuery(document).ready(function($){

      $(window).scroll(function() {
        
        console.log("asdf");

      if ($(window).scrollTop() > 100 ){
      
      $('.top-header').addClass('shows');
      
        } else {
      
        $('.top-header').removeClass('shows');
      
      };   	
    });

    });

  jQuery('.scroll').on('click', function(e){		
      e.preventDefault()
      
    jQuery('html, body').animate({
        scrollTop : jQuery(this.hash).offset().top
      }, 1500);
  });


</script>

```

これで再度動作確認を行なってみてください。

以上

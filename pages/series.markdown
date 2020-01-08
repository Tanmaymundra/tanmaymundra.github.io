---
layout: books
title: Tanmay Mundra - My Series Recommendations
permalink: about/series
---
<head>
	<link rel="stylesheet" type="text/css" href="/css/book_style.css" />
	<link rel="stylesheet" type="text/css" href="/css/books_component.css" />
		<!-- Modernizr is used for flexbox fallback -->
	<script src="/js/modernizr.custom.js"></script>
</head>
<div class="view">
	<div class="my__suggestion"><center><h1><br>Series I Would Recommend/ Watched</h1></center><div>
		<section class="grid">
		{% for serie in site.data.Series %}
			<div class="product">
				<div class="product__info">
					<img class="product__image" src="{{serie.image}}" alt="{{serie.title}}" />
					<h3 class="product__title">{{serie.title}}</h3>
					<span class="product__rating highlight">{{serie.Rating}}</span>
					<!--h4 class="product__rating"> {{serie.Rating}}</h4-->
					<button class="action action--button" onclick="window.open('{{serie.reviews}}')"><i class="fa fa-comments"></i><span class="action__text">Reviews</span></button>
				</div>
			</div>
		{% endfor %}				
		</section>
		<center>
			<h3>Bookworm eh? Follow me on <a href=""><img src="https://upload.wikimedia.org/wikipedia/commons/6/69/IMDB_Logo_2016.svg" height="60" width="60" /></a></h3>
		</center>
	</div>
</div>

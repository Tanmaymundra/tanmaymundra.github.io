---
layout: books
title: Tanmay Mundra - My Movies Recommendations
---
<head>
	<link rel="stylesheet" type="text/css" href="/books/css/book_style.css" />
	<link rel="stylesheet" type="text/css" href="/books/css/books_component.css" />
		<!-- Modernizr is used for flexbox fallback -->
	<script src="/books/js/modernizr.custom.js"></script>
</head>
<div class="view">
	<div class="my__suggestion"><center><h1><br>Movies I Would Recommend</h1></center><div>
		<section class="grid">
		{% for movie in site.data.movies %}
			<div class="product">
				<div class="product__info">
					<img class="product__image" src="{{movie.image}}" alt="{{movie.title}}" />
					<h3 class="product__title">{{movie.title}}</h3>
					<!--span class="product__author highlight">Paulo Coelho</span-->
					<button class="action action--button" onclick="window.open('{{movie.reviews}}')"><i class="fa fa-comments"></i><span class="action__text">Reviews</span></button>
				</div>
			</div>
		{% endfor %}				
		</section>
		<!--center>
			<h3>Bookworm eh? Follow me on <a href=""><img src="goodreads_logo.png" /></a></h3>
		</center-->
	</div>
</div>

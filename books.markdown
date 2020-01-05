---
layout: books
title: Tanmay Mundra - My Books Recommendations
---
<head>
	<link rel="stylesheet" type="text/css" href="/books/css/book_style.css" />
	<link rel="stylesheet" type="text/css" href="/books/css/books_component.css" />
		<!-- Modernizr is used for flexbox fallback -->
	<script src="js/modernizr.custom.js"></script>
</head>
<div class="view">
	<div class="my__suggestion"><center><h1><br>Books I Would Recommend</h1></center><div>
		<section class="grid">
		{% for book in site.data.books %}
			<div class="product">
				<div class="product__info">
					<img class="product__image" src="{{book.Image}}" alt="{{book.title}}" />
					<h3 class="product__title">{{book.title}}</h3>
					<span class="product__author highlight">{{book.author}}</span>
					<button class="action action--button" onclick="window.open('{{book.reviews}}')"><i class="fa fa-comments"></i><span class="action__text">Reviews</span></button>
				</div>
			</div>
		{% endfor %}				
		</section>
		<center>
			<h3>Bookworm eh? Follow me on <a href="https://www.goodreads.com/<username>"><!--img src="goodreads_logo.png" /--></a></h3>
		</center>
	</div>
</div>

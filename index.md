---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8" />
		<title></title>
		<style>
			*{
				margin: 0;
				padding: 0;
			}
			html,body{
				width: 100%;
				height:100%;
			}
			body{
				background: url(img/bg2.jpg);
				background-size: 100%;
			}
			div{
				width: 280px;
				height: 400px;
				position: fixed;
				top: 0;
				left:0;
				right: 0;
				bottom: 0;
				margin: auto;
				transform-style: preserve-3d;
				animation: play 60s linear infinite;
			}
			
			div img{
				width: 280px;
				height:400px;
				position: absolute;
			}
			
div img:nth-child(1){transform: rotateY(0deg) translatez(650px);}
div img:nth-child(2){transform: rotateY(36deg) translatez(650px);}
div img:nth-child(3){transform: rotateY(72deg) translatez(650px);}
div img:nth-child(4){transform: rotateY(108deg) translatez(650px);}
div img:nth-child(5){transform: rotateY(144deg) translatez(650px);}
div img:nth-child(6){transform: rotateY(180deg) translatez(650px);}
div img:nth-child(7){transform: rotateY(216deg) translatez(650px);}
div img:nth-child(8){transform: rotateY(252deg) translatez(650px);}
div img:nth-child(9){transform: rotateY(288deg) translatez(650px);}
div img:nth-child(10){transform: rotateY(324deg) translatez(650px);}
			
			@keyframes play{
				0%{transform: rotateX(0deg) rotateY(0deg);}
				25%{transform: rotateX(20deg) rotateY(180deg);}
				50%{transform: rotateX(0deg) rotateY(360deg);}
				75%{transform: rotateX(-20deg) rotateY(540deg);}
				100%{transform: rotateX(0deg) rotateY(720deg);}
			}
	
		</style>
	

<div class="left">
        <h1>Welcome to lengyanyu's blog </h1>
        <small>这里是我的个人IT学习小天地</small>
        <hr>
        <ul>
        	<!--遍历分页后的文章-->
           {% for post in paginator.posts %}
  		   <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
 		   <p class="author">
           	<span class="date">{{ post.date }}</span>
           </p>
    	   <div class="content">
    	   {{ post.content }}
  		   {% endfor %}
        </ul>
</div>
<div>
			<img src="img/pic1.jpg" />
			<img src="img/pic2.png" />
			<img src="img/pic3.png" />
			<img src="img/pic4.png" />
			<img src="img/pic5.jpg" />
			<img src="img/pic6.png" />
			<img src="img/pic7.png" />
			<img src="img/pic8.png" />
			<img src="img/pic9.png" />
			<img src="img/pic10.png" />
</div>
<audio src="raw/aaaaa.mp3" autoplay="autoplay"></audio>
<img src="img/a.gif" class="love" />



<div class="page clearfix" index>
    <div class="left">
        <h1>Welcome to lengyanyu's blog </h1>
        <small>这里是我的个人IT学习小天地</small>
        <hr>
        <ul>
        	<!--遍历分页后的文章-->
           {% for post in paginator.posts %}
  		   <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
 		   <p class="author">
           	<span class="date">{{ post.date }}</span>
           </p>
    	   <div class="content">
    	   {{ post.content }}
  		   {% endfor %}
        </ul>
    </div>




       <!--  <!-- Pagination links分页链接 -->
        <div class="pagination">
          <!--生成一个跳转到上一页的按钮-->	
          {% if paginator.previous_page %}
            <a href="/index.html" class="previous"><i class="fa fa-angle-double-left"></i>
            </a>
            <a href="{{ paginator.previous_page_path | prepend: site.baseurl }}" class="previous"><i class="fa fa-angle-left"></i></a>
          {% else %}
            <span class="previous disable"><i class="fa fa-angle-double-left"></i></span>
            <span class="previous disable"><i class="fa fa-angle-left"></i></span>
          {% endif %}
          <span class="page_number ">{{ paginator.page }}/{{ paginator.total_pages }}</span>

          <!--生成一个下一页的按钮-->
          {% if paginator.next_page %}
            <a href="{{ paginator.next_page_path }}" class="next"><i class="fa fa-angle-right"></i></a>
            <a href="{{ site.baseurl }}/page{{ paginator.total_pages }}" class="next"><i class="fa fa-angle-double-right"></i></a>
          {% else %}
            <span class="next disable"><i class="fa fa-angle-right"></i></span>
            <span class="next disable"><i class="fa fa-angle-double-right"></i></span>
          {% endif %}
        </div>
    </div>
    <!-- <button class="anchor"><i class="fa fa-anchor"></i></button> -->
    <div class="right">
        <div class="wrap">
            <div class="side">
                <div>
                    <i class="fa fa-pencil-square-o" aria-hidden="true"></i>
                    Recent Posts
                </div>
                <ul class="content-ul" recent>
                    {% for post in site.posts offset: 0 limit: 10  %}
                        <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
                    {% endfor %}
                </ul>
            </div>

            <!-- Content -->
            <div class="side ">
                <div>
                    <i class="fa fa-th-list"></i>
                    Categories
                </div>
                <ul class="content-ul" cate>
                    {% for category in site.categories %}
                    <li>
                        <a href="{{ root_url }}/{{ site.category_dir }}#{{ category | first }}" class="categories-list-item" cate="{{ category | first }}">
                            <span class="name">
                                {{ category | first }}
                            </span>
                            <span class="badge">{{ category | last | size }}</span>
                        </a>
                    </li>
                    {% endfor %}
                </ul>
            </div>
           
# lazyload
Image Load on visible , Lazy Image load | jquey | javascript


on Image use "data-src" instand of "src"
<img src="path"> 
<img data-src="path">


In Javascript or Jquery (Both versitons are available) Copy those script !
and Must use Preloder.gif img to Preloder

Place_holder_image = loaderImage.gif // must have to download the gift img 




How to Use:
1. use data-src 
2. past those Script 
3. do not use $(document).ready();
4. Need a Cdn or download Jquey (if use jquery code);
5. Demo are also there.





    var Place_holder_image = 'img/load.gif'; // All Image For the Place Holder
    
        $('img').attr('src',Place_holder_image);
        $(window).scroll(lazyload);
        $(document).ready(lazyload);
        
		function lazyload(){
			$('img').each(function(){
				var src_img = $(this).attr('data-src');
				if(elementInViewPort(this)){
					$(this).attr('src',src_img);
				}
			});
		}
		function elementInViewPort(el){
			var rect = el.getBoundingClientRect();
			return (
			rect.top >= 0 &&
			 rect.left >= 0 && 
			 rect.bottom <= (window.innerHeight ||document.documentElement.clientHeight) && 
			 rect.right <= (window.innerWidth || document.documentElement.clientWidth)
			);
		}

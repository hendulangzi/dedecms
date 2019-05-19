# dedecms
<?=$cfg_webname?>
{dede:global.cfg_webname/}

    {dede:include filename="head_new.htm"/}
    {dede:include filename="footer_new.htm"/}
	//某个分类名称
	{dede:type typeid="9"}
       <a href="[field:typeurl/]">[field:typename/]</a>
    {/dede:type}
    //文章标题，网站名称
    <title>{dede:field.title/} - {dede:global.cfg_webname/}</title>
    //关键词
    <meta name="keywords" content="{dede:field name='keywords'/}" />
    //描述
    <meta name="description" content="{dede:field name='description' function='html2text(@me)'/}" />
	
	//文章标题
	{dede:field.title/}
	//文章内容
	 {dede:field.body/}
	 {dede:field.content/}
	 //时间转换
	 [field:pubdate function='strftime("%m-%d",@me)'/]
	 
	 //某个分类下的文章
	 {dede:list pagesize='10'}
	  <li> 
	   <div class="inner"> 
		<span class="text-list-a"> <code></code><a href="[field:arcurl/]" title="[field:title/]">[field:title/]</a> </span> 
		<span class="text-list-times">[field:pubdate function="GetDateTimeMK(@me)"/]</span> 
	   </div></li> 
	  {/dede:list}
	 {dede:pagelist listitem="index,end,pre,next,pageno" listsize="5"/}
	 //某个指定分类文章
	 {dede:arclist orderby=pubdate typeid=10 row=15}
             <li>
              <div class="inner">
                <span class="text-list-times">[field:pubdate function="MyDate('Y-m-d',@me)"/]</span>
               <span class="text-list-a">
                 <code></code><a class=""  href="[field:arcurl/]"   title="[field:title/]">[field:title/]</a>
               </span>
              </div>
             </li>
             {/dede:arclist}
	//上一页
	{dede:prenext get='pre'/} 
	//下一页
	{dede:prenext get='next'/}
	//分页内容
	{dede:pagelist listitem="index,end,pre,next,pageno" listsize="5"/}


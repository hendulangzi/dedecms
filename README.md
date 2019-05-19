# dedecms
<?=$cfg_webname?>
{dede:global.cfg_webname/}

    {dede:include filename="head_new.htm"/}
    {dede:include filename="footer_new.htm"/}
	
	{dede:type typeid="9"}
       <a href="[field:typeurl/]">[field:typename/]</a>
    {/dede:type}
    <title>{dede:field.title/} - {dede:global.cfg_webname/}</title>
    <meta name="keywords" content="{dede:field name='keywords'/}" />
    <meta name="description" content="{dede:field name='description' function='html2text(@me)'/}" />
	
	{dede:field.title/}
	 {dede:field.body/}
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

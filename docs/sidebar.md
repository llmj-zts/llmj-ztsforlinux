- [安装ArchLinux](/home/install.md)
- [系统环境](/home/system.md)
- [系统美化](/home/beautify.md)
- [爽玩游戏](/home/game.md)
- [食用工具](/home/tool.md)
- [其他网站](//zts.llmj.dpdns.org/html/fifth.html)
- [个人笔记](/home/note.md)
- [关于](home/)

<script>
  $.getJSON("https://zts.llmj.dpdns.org/picture/img.json",function(data){
    const backgroundimg=data;
    const rand=Math.floor(Math.random()*backgroundimg.length);
    var ment=document.createElement("img");
    ment.src='url('+backgroundimg[rand].url+')';
    ment.alt="backgroundimg";
    document.body.appendChild(ment);
    })
</script>

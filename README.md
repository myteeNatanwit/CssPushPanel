Css push panel
==============

Very simple left side push panel as seen in FB, GG, ...  used in 1001 Jokes app on Appstore and GGplay.

Screen shot here
http://i1363.photobucket.com/albums/r708/MyteeNathanwit/slidemenu_zps53933e89.png

The we need to define 2 classes the leftpanel and the mainpanel -or container, or whatever that is the main screen-.
they both need to have the transform set to get the smooth transaction.
ie ...   -webkit-transition: -webkit-transform 0.2s ease-in;

"
#leftpanel
{
-webkit-transition: -webkit-transform 0.2s ease-in; // smooth move
position: absolute; // required
left: 0; top: 0; width: 40%; height: 100%;
background: #333; //dark gray
-webkit-transform: translate3d(-100%,0,0); // hide it outside canvas by move it far to left
transform: translate3d(-100%,0,0);
}
#leftpanel.sliding{
-webkit-transform: translate3d(0,0,0); // move back to view
}
#mainpanel {
-webkit-transition: -webkit-transform 0.2s ease-in;  // smooth move
}
// we need to add a class to toogle the action
#leftpanel.sliding {
-webkit-transform: translate3d(40%,0,0); //move to the right make room for left panel
}
//and a button or so to triggle the panel
#menubtn:hover{
opacity: 1;
}
#menubtn{
background: url(images/menu.png) no-repeat;
position: absolute;  
top:4px; left:4px;
width:40px; height:40px; 
opacity: 0.5;
}
"
That is all folk. very simple. Now we need to get the element in action with Jquery. You can use any version of Jquery.
...
<script type="text/javascript" src="js/jquery-1.5.2.min.js"></script>
<body>
<div id="leftpanel" onclick="$('#leftpanel,#mainpanel').toggleClass('sliding')"> // we just force the element to response with a click,
note that there are 2 panels trigger here.
// this is my about box, you replace them with whatever you like, a list of options for example

<div id="about" style="border:1px solid gray; margin: 10% 5px; text-align:center;">
<img style="float:left;margin:5px;margin-left: 10%" src="images/icon.png" />
<h3>Myteezine ver <span id="version">1.5.0</span><br> Written by Mytee<br>  </h3> 
<h4>Copyright � 2013-2014 <a href="http://intcloud.mobi">IntCloud</a> All rights reserved</h4>
</div>
</div>

<div id="mainpanel" style=" width:100%; height:100%; overflow:hidden;">
<div id="menubtn" onclick="$('#leftpanel,#mainpanel').toggleClass('sliding')"></div>
...
</body>

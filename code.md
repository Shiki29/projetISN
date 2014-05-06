int x1=141;  //En haut à droite (13;13)    +  64
int y1=13;
int x2=13;
int y2=205;
int x3=141;
int y3=205;
int x4=269;
int y4=205;
int l=119;
int h=55;

void setup() {
  size(400, 400);
  
}

void draw() { //s'applique 30 fois par secondes

// /!\ Trouvé sur l'internet /!\
  background(175); // couleur de l'arriere-plan
  
  fill(200);
  int largeurColonne = width/6-2;
  int hauteurRangee = height/6-2;

  //////////////// Dessiner la grille du fond /////////////
  for(int i=0 ; i < 6 ; i++){ 
    for(int j=0 ; j < 6 ; j++){ 
      int x = i*largeurColonne+10;
      int y = j*hauteurRangee+10;
      rect( x+1 , y+1 , largeurColonne-5 , hauteurRangee-5 );
    }
  }
// /!\ Fin du Trouvé sur l'internet /!\

fill (255,0,0);
rect(x1, y1, h, l);
fill (0,255,0);
rect(x2, y2, l, h);
fill (0,0,255);
rect(x3,y3,l,h);
fill (235,125,255);
rect(x4,y4,l,h);

//VICTOIRE !
if (333<x2+l && x2+l<397){
  background(133,158,165); 
}


}

void mouseDragged() { //s'applique quand la souris est tirée

  // Partie pour la voiture 1:
  if (mouseX>x1 && mouseX<x1+h && mouseY>y1 && mouseY<y1+l){
     if (y1 > y2 && y1 < y2+h && x1+h > x2 && x1 < x2+l || y1> y3 && y1 < y3+h && x1+h > x3 && x1 < x3+l){
      y1=y1+1;
     }

     else if (y1 < y2 && y1+l > y2 && x1+h > x2 && x1 < x2+l || y1 < y3 && y1+l > y3 && x1+h > x3 && x1 < x3+l){
       y1=y1-1;
     }
     else {
      y1=mouseY-(l/2);
     }

  }
  //Partie pour la voiture 2 :
  if (mouseX>x2 && mouseX<x2+l && mouseY>y2 && mouseY<y2+h){
     if (x2 > x1 && x2 < x1+h && y2+h > y1 && y2 < y1+l){
      x2=x2+1;
     }

   else if (x2 < x1 && x2+l > x1 && y2+h > y1 && y2 < y1+l || x2+l>x3){
       x2=x2-1;
     }
     else {
       x2=mouseX-(l/2);
     }

  }
  
 //Partie voiture 3 :
 if (mouseX>x3 && mouseX<x3+l && mouseY>y3 && mouseY<y3+h){
     if (x3 > x1 && x3 < x1+h && y3+h > y1 && y3 < y1+l || x3<x2+l){
      x3=x3+1;
     }
     else if (x3 < x1 && x3+l > x1 && y3+h > y1 && y3 < y1+l){
       x3=x3-1;
     }
     else {
       x3=mouseX-(l/2);
     }

    }
  


}


/* VOITURE VERTICALE PAR RAPPORT A VOITURE HORIZONTALE


  if (mouseX>xVerti && mouseX<xVerti+h && mouseY>yVerti && mouseY<yVerti+l){
   if (yVerti>yHori){
     if (yVerti < yHori+h && xVerti+h > xHori && xVerti < xHori+l){
      yVerti=yVerti+1;
     }
     else {
      yVerti=mouseY-(l/2);
     }
   }
   else{
     if (yVerti+l > yHori && xVerti+h > xHori && xVerti < xHori+l){
       yVerti=yVerti-1;
     }
     else {
      yVerti=mouseY-(l/2);
     }

    }
    
  }
  
  */
  
/* VOITURE HORIZONTALE PAR RAPPORT A VOITURE VERTICALE

 if (mouseX>xHori && mouseX<xHori+l && mouseY>yHori && mouseY<yHori+h){
   if (xHori>xVerti){
     if (xHori < xVerti+h && yHori+h > yVerti && yHori < yVerti+l){
      xHori=xHori+1;
     }
     else {
       xHori=mouseX-(l/2);
     }
   }
   else{
     if (xHori+l > x1 && yHori+h > yVerti && yHori < yVerti+l){
       xHori=xHori-1;
     }
     else {
       xHori=mouseX-(l/2);
     }

    }
  }
}
*/

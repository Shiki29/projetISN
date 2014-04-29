int x1=10;
int y1=100;
int x2=250;
int y2=100;
int l=100;
int h=40;

void setup() {
  size(400, 400);
  
}

void draw() { //s'applique 30 fois par secondes

// /!\ Trouvé sur l'internet /!\
  background(175); // couleur de l'arriere-plan
  
  fill(200);
  int largeurColonne = width/6-2;
  int hauteurRangee = height/6-2;

  //////////////// Dessinfepjdo fond /////////////
  for(int i=0 ; i < 6 ; i++){ 
    for(int j=0 ; j < 6 ; j++){ 
      int x = i*largeurColonne+10;
      int y = j*hauteurRangee+10;
      rect( x+1 , y+1 , largeurColonne-5 , hauteurRangee-5 );
    }
  }
// /!\ Fin du Trouvé sur l'internet /!\

fill (255,0,0);
rect(x1, y1, l, h);
fill (0,255,0);
rect(x2, y2, l, h);

}

void mouseDragged() { //s'applique quand la souris est tirée
  if (mouseX>x1 && mouseX<x1+l && mouseY>y1 && mouseY<y1+h){
    x1=mouseX-(l/2);
    y1=100; //y1=mouseY-(h/2);
  }
  if (mouseX>x2 && mouseX<x2+l && mouseY>y2 && mouseY<y2+h){
   if (x2 > x1+l || x2 < x1-l){
    x2=mouseX-(l/2);
    y2=100; //y2=mouseY-(h/2);
   }
   else {
     x1=x2-(l+1);
   }

  }

  }
 

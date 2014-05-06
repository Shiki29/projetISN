int xCJaune=141;  //En haut à droite (13;13)    +  64
int yCJaune=13;

int xVRouge=13;
int yVRouge=141;

int xVVerte=269;
int yVVerte=13;

int xCMauve=13;
int yCMauve=205;

int xCBleu=333;
int yCBleu=205;

int lv=119;

int lc=183;

int h=55;

boolean niveau1 = true;

void setup() {
  size(400, 400);
  
}

void draw() { //s'applique 30 fois par secondes

  dessiner();


if (niveau1 = true){
  
  niveau1();
  
}




}
void dessiner() {
  
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
}
// /!\ Fin du Trouvé sur l'internet /!\
void niveau1() {

fill (241,250,18);
rect(xCJaune, yCJaune, h, lc);

fill (255,0,0);
rect(xVRouge, yVRouge, lv, h);

fill (0,162,20);
rect(xVVerte,yVVerte,lv,h);

fill (173,51,211);
rect(xCMauve,yCMauve,lc,h);

fill (0,10,245);
rect(xCBleu,yCBleu,h,lc);

//VICTOIRE !
if (333<xVRouge+lv && xVRouge+lv<397){
  background(133,158,165); 
  delay(3000);
  background(255,0,0);
}



if (mousePressed){

  // Partie Camion Jaune:
  if (mouseX>xCJaune && mouseX<xCJaune+h && mouseY>yCJaune && mouseY<yCJaune+lv){
    if (mouseY-(lc/2) > 11 && mouseY-(lc/2)+lc < 391){
      if (mouseY-(lc/2)+lc < yVRouge || mouseY-(lc/2) > yVRouge+h || xCJaune+h < xVRouge || xCJaune > xVRouge+lv){
        if(mouseY-(lc/2)+lc < yCMauve || mouseY-(lc/2) > yCMauve+h || xCJaune+h < xCMauve || xCJaune > xCMauve+lc){
          if(mouseY-(lc/2)+lc < yVVerte || mouseY-(lc/2) > yVVerte+h || xCJaune+h < xVVerte || xCJaune > xVVerte+lv){
            yCJaune=mouseY-(lc/2);
          }
        }
      }
    }
  }
  
  // Partie Camion Bleu:
  if (mouseX>xCBleu && mouseX<xCBleu+h && mouseY>yCBleu && mouseY<yCBleu+lv){
    if (mouseY-(lc/2) > 11 && mouseY-(lc/2)+lc < 391){
      if (mouseY-(lc/2)+lc < yVRouge || mouseY-(lc/2) > yVRouge+h || xCBleu+h < xVRouge || xCBleu > xVRouge+lv){
        if(mouseY-(lc/2)+lc < yCMauve || mouseY-(lc/2) > yCMauve+h || xCBleu+h < xCMauve || xCBleu > xCMauve+lc){
          if(mouseY-(lc/2)+lc < yVVerte || mouseY-(lc/2) > yVVerte+h || xCBleu+h < xVVerte || xCBleu > xVVerte+lv){
            yCBleu=mouseY-(lc/2);
          }
        }
      }
    }
  }
 
  //Partie Voiture Rouge :
  if (mouseX>xVRouge && mouseX<xVRouge+lv && mouseY>yVRouge && mouseY<yVRouge+h){
    if (mouseX-(lv/2) > 11 && mouseX-(lv/2)+lv < 391){
      if (mouseX-(lv/2)+lv < xCJaune || mouseX-(lv/2) > xCJaune+h || yVRouge+h < yCJaune || yVRouge > yCJaune+lc){
        if (mouseX-(lv/2)+lv < xCBleu || mouseX-(lv/2) > xCBleu+h || yVRouge+h < yCBleu || yVRouge > yCBleu+lc){
          xVRouge=mouseX-(lv/2);
        }
      }
    }
  }
  
 //Partie Voiture Verte :
 if (mouseX>xVVerte && mouseX<xVVerte+lv && mouseY>yVVerte && mouseY<yVVerte+h){
    if (mouseX-(lv/2) > 11 && mouseX-(lv/2)+lv < 391){
      if (mouseX-(lv/2)+lv < xCJaune || mouseX-(lv/2) > xCJaune+h || yVVerte+h < yCJaune || yVVerte > yCJaune+lc){
        if (mouseX-(lv/2)+lv < xCBleu || mouseX-(lv/2) > xCBleu+h || yVVerte+h < yCBleu || yVVerte > yCBleu+lc){
          xVVerte=mouseX-(lv/2);
        }
      }
    }
  }
 
  //Partie Camion Mauve :
 if (mouseX>xCMauve && mouseX<xCMauve+lv && mouseY>yCMauve && mouseY<yCMauve+h){
    if (mouseX-(lc/2) > 11 && mouseX-(lc/2)+lc < 391){
      if (mouseX-(lc/2)+lc < xCJaune || mouseX-(lc/2) > xCJaune+h || yCMauve+h < yCJaune || yCMauve > yCJaune+lc){
        if (mouseX-(lc/2)+lc < xCBleu || mouseX-(lc/2) > xCBleu+h || yCMauve+h < yCBleu || yCMauve > yCBleu+lc){
          xCMauve=mouseX-(lc/2);
        }
      }
    }
  }
  
}
}

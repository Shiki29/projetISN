
// Valeur longueur voiture
int lv=119;
// Valeur longueur camion
int lc=183;
// Valeur hauteur véhicules
int h=55;

boolean niveau1 = true;

// Coordonnées véhicules niveau 1
int xCJaune1=141;  //En haut à droite (13;13)    +  64
int yCJaune1=13;

int xVRouge1=13;
int yVRouge1=141;

int xVVerte1=269;
int yVVerte1=13;

int xCMauve1=13;
int yCMauve1=205;

int xCBleu1=333;
int yCBleu1=205;

void setup() {
  size(400, 400);
}

void draw() { //s'applique 30 fois par secondes
  
  dessiner();


  if (niveau1 == true){
  
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

  // Camion Jaune (Vertical)
  fill (241,250,18);
  rect(xCJaune1, yCJaune1, h, lc);

  // Voiture Rouge (Horizontale)
  fill (255,0,0);
  rect(xVRouge1, yVRouge1, lv, h);

  // Voiture Verte (Horizontale)
  fill (0,162,20);
  rect(xVVerte1,yVVerte1,lv,h);

  // Camion Mauve (Horizontal)
  fill (173,51,211);
  rect(xCMauve1,yCMauve1,lc,h);

  //Camion Bleu (Vertical)
  fill (0,10,245);
  rect(xCBleu1,yCBleu1,h,lc);

  // Condition de victoire et passage au niveau suivant
  if (365<xVRouge1+lv && xVRouge1+lv<397){
    background(255,0,0);
    niveau1 = false;
  }



  if (mousePressed){

    // Partie Camion Jaune:
    if (mouseX>xCJaune1 && mouseX<xCJaune1+h && mouseY>yCJaune1 && mouseY<yCJaune1+lv){
      if (mouseY-(lc/2) > 11 && mouseY-(lc/2)+lc < 391){
        if (mouseY-(lc/2)+lc < yVRouge1 || mouseY-(lc/2) > yVRouge1+h || xCJaune1+h < xVRouge1 || xCJaune1 > xVRouge1+lv){
          if(mouseY-(lc/2)+lc < yCMauve1 || mouseY-(lc/2) > yCMauve1+h || xCJaune1+h < xCMauve1 || xCJaune1 > xCMauve1+lc){
            if(mouseY-(lc/2)+lc < yVVerte1 || mouseY-(lc/2) > yVVerte1+h || xCJaune1+h < xVVerte1 || xCJaune1 > xVVerte1+lv){
              yCJaune1=mouseY-(lc/2);
            }
          }
        }
      }
    }
  
    // Partie Camion Bleu:
    if (mouseX>xCBleu1 && mouseX<xCBleu1+h && mouseY>yCBleu1 && mouseY<yCBleu1+lv){
      if (mouseY-(lc/2) > 11 && mouseY-(lc/2)+lc < 391){
        if (mouseY-(lc/2)+lc < yVRouge1 || mouseY-(lc/2) > yVRouge1+h || xCBleu1+h < xVRouge1 || xCBleu1 > xVRouge1+lv){
          if(mouseY-(lc/2)+lc < yCMauve1 || mouseY-(lc/2) > yCMauve1+h || xCBleu1+h < xCMauve1 || xCBleu1 > xCMauve1+lc){
            if(mouseY-(lc/2)+lc < yVVerte1 || mouseY-(lc/2) > yVVerte1+h || xCBleu1+h < xVVerte1 || xCBleu1 > xVVerte1+lv){
              yCBleu1=mouseY-(lc/2);
            }
          }
        }
      }
    }
 
    //Partie Voiture Rouge :
    if (mouseX>xVRouge1 && mouseX<xVRouge1+lv && mouseY>yVRouge1 && mouseY<yVRouge1+h){
      if (mouseX-(lv/2) > 11 && mouseX-(lv/2)+lv < 391){
        if (mouseX-(lv/2)+lv < xCJaune1 || mouseX-(lv/2) > xCJaune1+h || yVRouge1+h < yCJaune1 || yVRouge1 > yCJaune1+lc){
          if (mouseX-(lv/2)+lv < xCBleu1 || mouseX-(lv/2) > xCBleu1+h || yVRouge1+h < yCBleu1 || yVRouge1 > yCBleu1+lc){
            xVRouge1=mouseX-(lv/2);
          }
        }
      }
    }
  
   //Partie Voiture Verte :
   if (mouseX>xVVerte1 && mouseX<xVVerte1+lv && mouseY>yVVerte1 && mouseY<yVVerte1+h){
      if (mouseX-(lv/2) > 11 && mouseX-(lv/2)+lv < 391){
        if (mouseX-(lv/2)+lv < xCJaune1 || mouseX-(lv/2) > xCJaune1+h || yVVerte1+h < yCJaune1 || yVVerte1 > yCJaune1+lc){
          if (mouseX-(lv/2)+lv < xCBleu1 || mouseX-(lv/2) > xCBleu1+h || yVVerte1+h < yCBleu1 || yVVerte1 > yCBleu1+lc){
            xVVerte1=mouseX-(lv/2);
          }
        }
      }
    }
 
   //Partie Camion Mauve :
   if (mouseX>xCMauve1 && mouseX<xCMauve1+lv && mouseY>yCMauve1 && mouseY<yCMauve1+h){
      if (mouseX-(lc/2) > 11 && mouseX-(lc/2)+lc < 391){
        if (mouseX-(lc/2)+lc < xCJaune1 || mouseX-(lc/2) > xCJaune1+h || yCMauve1+h < yCJaune1 || yCMauve1 > yCJaune1+lc){
          if (mouseX-(lc/2)+lc < xCBleu1 || mouseX-(lc/2) > xCBleu1+h || yCMauve1+h < yCBleu1 || yCMauve1 > yCBleu1+lc){
            xCMauve1=mouseX-(lc/2);
          }
        }
      }
    }
    
  }
  
}

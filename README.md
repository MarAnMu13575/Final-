# Final-
#include <Magick++.h> 
#include <iostream> 
using namespace std; 
using namespace Magick;

void newline(){
  cout<<endl;
}

int main(int argc,char **argv) 
{ 
  InitializeMagick(*argv);
  try{
  int x;
  cout<<"Hi, Im a manipulator of images "<<endl;
  newline();
  cout<<"What do you want to do? (press the number in your keyboard) "<<endl;
  newline();
  cout<<"1. Rezise the image to one half of its original size"<<endl;
  cout<<"2. Switch to black and white"<<endl;
  newline();
  cin>>x;
  
  if(x==1){
     newline();
     cout<<"Alright, now introduce the name of the file with its extension; example: new.jpg"<<endl;  
     newline();
     Image image;
     string img;
     cin>>img;
     image.read(img);
     image.minify();
     image.write("resized.jpg");
 }
  if(x==2){
     newline();
     cout<<"Alright, now introduce the name of the file with its extension; example: new.jpg"<<endl;  
     newline();
     Image image;
     string img2;
     cin>>img2;
     image.read(img2);
     image.quantize(colorspace.gray);
     image.write("blackandwhite.jpg");
 }       
 } 
  catch( Exception &error_ ) 
    { 
      cout << "Caught exception: " << error_.what() << endl; 
      return 1; 
    } 
  return 0; 
}

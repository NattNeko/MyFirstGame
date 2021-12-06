# MyFirstGame#


## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Screenshots](#screenshots)
* [Setup](#setup)
* [Usage](#usage)
* [Project Status](#project-status)
* [Acknowledgements](#acknowledgements)




## General Information
- "Flying Animals" is a game made by me.
- I did it as a project for programming lesson.



## Technologies Used
- Microsoft Visual Studio Community 2019 - Version 16.8.4


## Screenshots
(![image](https://user-images.githubusercontent.com/80109525/144935810-e9788a76-5de6-4707-8009-ec1d270b3441.png)
./img/screenshot.png)



## Setup
How to open the game:
Open NataliaNagorka.7z -> NataliaNagorka -> bin -> Debug -> NataliaNagorka.exe


## Usage
(C#)

using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Media;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace NataliaNagorka
{
    public partial class Form1 : Form
    {
        int lolipopSpeed = 8;
        int gravity = 15;
        int score = 0;
        int click = 0;

        
        public Form1()
        {
            InitializeComponent();
            
        }
        





        private void gamekeyisdown(object sender, KeyEventArgs e)
        {
            if (e.KeyCode == Keys.R)
            {
                Application.Restart();
            }
            if (e.KeyCode == Keys.D)
            {
                    
               doggy.Visible = true;
               animal.Visible = false;
                
            }
            if (e.KeyCode == Keys.C)
            {
                doggy.Visible = false;
                animal.Visible = true;

            }

            if (e.KeyCode == Keys.Space)
            {
                
                gravity = -15;
            }


        }
        
        
            private void gamekeyisup(object sender, KeyEventArgs e)
            {
                

                if (e.KeyCode == Keys.C)
                {
                 

                doggy.Visible = false;
                animal.Visible = true;

                }

            if (e.KeyCode == Keys.D)
            {
                doggy.Visible = true;
                animal.Visible = false;
            }


            if (e.KeyCode == Keys.Space)
                {
                    click++;
                    gravity = 15;
                }

            }
        
        private void endGame()
        {
           

            Czas_grania.Stop();
            punkty.Text += " Koniec gry!";
        }

        private void Czas_graniaEvent(object sender, EventArgs e)
        {
            
            animal.Top += gravity;
            doggy.Top += gravity;
            lolipopdown.Left -= lolipopSpeed;
            lolipopup.Left -= lolipopSpeed;
            lolipop1.Left -= lolipopSpeed;
            lolipop2.Left -= lolipopSpeed;
            lolipop3.Left -= lolipopSpeed;
            lolipop4.Left -= lolipopSpeed;
            punkty.Text = "Punkty: " + score;
            kilknięcia.Text = "Kliknięcia: " + click; 



            if (lolipopdown.Left < -150)
            {

                lolipopdown.Left = 800;
                score++;
                licznik.PerformStep();
            }
            if (lolipopup.Left < -180)
            {

                lolipopup.Left = 950;
                score++;
                licznik.PerformStep();
            }
            if (lolipop1.Left < -150)
            {

                lolipop1.Left = 800;
                score++;
                licznik.PerformStep();
            }
            if (lolipop2.Left < -180)
            {

                lolipop2.Left = 950;
                score++;
                licznik.PerformStep();
            }
            if (lolipop3.Left < -150)
            {

                lolipop3.Left = 800;
                score++;
                licznik.PerformStep();
            }
            if (lolipop4.Left < -180)
            {

                lolipop4.Left = 950;
                score++;
                licznik.PerformStep();
            }
            




            if (animal.Bounds.IntersectsWith(lolipopdown.Bounds) ||
                animal.Bounds.IntersectsWith(lolipopup.Bounds) ||
                animal.Bounds.IntersectsWith(lolipop1.Bounds) ||
                animal.Bounds.IntersectsWith(lolipop4.Bounds) ||
                animal.Bounds.IntersectsWith(lolipop3.Bounds) ||
                animal.Bounds.IntersectsWith(lolipop2.Bounds) ||
                animal.Bounds.IntersectsWith(ground.Bounds) || 
                animal.Top < -25 || 
                doggy.Top < -25 || 
                doggy.Bounds.IntersectsWith(lolipopdown.Bounds) ||
                doggy.Bounds.IntersectsWith(lolipopup.Bounds) ||
                doggy.Bounds.IntersectsWith(lolipop1.Bounds) ||
                doggy.Bounds.IntersectsWith(lolipop4.Bounds) ||
                doggy.Bounds.IntersectsWith(lolipop3.Bounds) ||
                doggy.Bounds.IntersectsWith(lolipop2.Bounds) ||
                doggy.Bounds.IntersectsWith(ground.Bounds)
                )
                
            {

                endGame();
            }
            


            if (score > 5)
            {
                lolipopSpeed = 15;
            }
            if (score > 20 )
            {
                lolipopSpeed = 25;
            }
            if (score > 50)
            {
                lolipopSpeed = 40;

            }
        }

        
    }
}


## Project Status
Project is: complete




## Acknowledgements
Give credit here.
- This project was inspired by Nguyễn Hà Đông's game Flappy Bird
- Many thanks to Tomasz for making textures for this game



# pac-man-python
{\rtf1\ansi\ansicpg1252\cocoartf2513
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fnil\fcharset0 Menlo-Italic;\f1\fnil\fcharset0 Menlo-Regular;\f2\fnil\fcharset0 Menlo-Bold;
}
{\colortbl;\red255\green255\blue255;\red123\green71\blue5;\red234\green234\blue234;\red47\green51\blue57;
\red5\green52\blue78;\red0\green0\blue0;\red69\green29\blue1;\red64\green140\blue9;\red133\green0\blue2;
}
{\*\expandedcolortbl;;\cssrgb\c56078\c34902\c784;\cssrgb\c93333\c93333\c93333;\cssrgb\c24314\c26275\c28627;
\cssrgb\c0\c26667\c38039;\cssrgb\c0\c0\c0;\cssrgb\c34510\c15686\c0;\cssrgb\c30588\c60392\c2353;\cssrgb\c60000\c0\c0;
}
\margl1440\margr1440\vieww10800\viewh8400\viewkind0
\deftab720
\pard\pardeftab720\partightenfactor0

\f0\i\fs30\fsmilli15300 \cf2 \cb3 \expnd0\expndtw0\kerning0
"""Pacman, classic arcade game.
\f1\i0 \cf4 \
\

\f0\i \cf2 Exercises
\f1\i0 \cf4 \
\

\f0\i \cf2 1. Change the board.
\f1\i0 \cf4 \

\f0\i \cf2 2. Change the number of ghosts.
\f1\i0 \cf4 \

\f0\i \cf2 3. Change where pacman starts.
\f1\i0 \cf4 \

\f0\i \cf2 4. Make the ghosts faster/slower.
\f1\i0 \cf4 \

\f0\i \cf2 5. Make the ghosts smarter.
\f1\i0 \cf4 \
\

\f0\i \cf2 """
\f1\i0 \cf4 \
\
\pard\pardeftab720\partightenfactor0

\f2\b \cf5 from
\f1\b0 \cf4  random 
\f2\b \cf5 import
\f1\b0 \cf4  choice\

\f2\b \cf5 from
\f1\b0 \cf4  turtle 
\f2\b \cf5 import
\f1\b0 \cf4  \cf7 *\cf4 \

\f2\b \cf5 from
\f1\b0 \cf4  freegames 
\f2\b \cf5 import
\f1\b0 \cf4  floor
\f2\b ,
\f1\b0  vector\
\
state \cf7 =\cf4  
\f2\b \{
\f1\b0 \cf8 'score'
\f2\b \cf4 :
\f1\b0  \cf9 0
\f2\b \cf4 \}
\f1\b0 \
path \cf7 =\cf4  Turtle
\f2\b (
\f1\b0 visible\cf7 =
\f2\b \cf5 False\cf4 )
\f1\b0 \
writer \cf7 =\cf4  Turtle
\f2\b (
\f1\b0 visible\cf7 =
\f2\b \cf5 False\cf4 )
\f1\b0 \
aim \cf7 =\cf4  vector
\f2\b (
\f1\b0 \cf9 5
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 )
\f1\b0 \
pacman \cf7 =\cf4  vector
\f2\b (
\f1\b0 \cf7 -\cf9 40
\f2\b \cf4 ,
\f1\b0  \cf7 -\cf9 80
\f2\b \cf4 )
\f1\b0 \
ghosts \cf7 =\cf4  
\f2\b [
\f1\b0 \
    
\f2\b [
\f1\b0 vector
\f2\b (
\f1\b0 \cf7 -\cf9 180
\f2\b \cf4 ,
\f1\b0  \cf9 160
\f2\b \cf4 ),
\f1\b0  vector
\f2\b (
\f1\b0 \cf9 5
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 )],
\f1\b0 \
    
\f2\b [
\f1\b0 vector
\f2\b (
\f1\b0 \cf7 -\cf9 180
\f2\b \cf4 ,
\f1\b0  \cf7 -\cf9 160
\f2\b \cf4 ),
\f1\b0  vector
\f2\b (
\f1\b0 \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 5
\f2\b \cf4 )],
\f1\b0 \
    
\f2\b [
\f1\b0 vector
\f2\b (
\f1\b0 \cf9 100
\f2\b \cf4 ,
\f1\b0  \cf9 160
\f2\b \cf4 ),
\f1\b0  vector
\f2\b (
\f1\b0 \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf7 -\cf9 5
\f2\b \cf4 )],
\f1\b0 \
    
\f2\b [
\f1\b0 vector
\f2\b (
\f1\b0 \cf9 100
\f2\b \cf4 ,
\f1\b0  \cf7 -\cf9 160
\f2\b \cf4 ),
\f1\b0  vector
\f2\b (
\f1\b0 \cf7 -\cf9 5
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 )],
\f1\b0 \

\f2\b ]
\f1\b0 \
tiles \cf7 =\cf4  
\f2\b [
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 1
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \
    \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ,
\f1\b0 \

\f2\b ]
\f1\b0 \
\

\f2\b \cf5 def
\f1\b0 \cf4  square
\f2\b (
\f1\b0 x
\f2\b ,
\f1\b0  y
\f2\b ):
\f1\b0 \
    \cf8 "Draw square using path at (x, y)."\cf4 \
    path\cf7 .\cf4 up
\f2\b ()
\f1\b0 \
    path\cf7 .\cf4 goto
\f2\b (
\f1\b0 x
\f2\b ,
\f1\b0  y
\f2\b )
\f1\b0 \
    path\cf7 .\cf4 down
\f2\b ()
\f1\b0 \
    path\cf7 .\cf4 begin_fill
\f2\b ()
\f1\b0 \
\
    
\f2\b \cf5 for
\f1\b0 \cf4  count 
\f2\b \cf5 in
\f1\b0 \cf4  \cf5 range
\f2\b \cf4 (
\f1\b0 \cf9 4
\f2\b \cf4 ):
\f1\b0 \
        path\cf7 .\cf4 forward
\f2\b (
\f1\b0 \cf9 20
\f2\b \cf4 )
\f1\b0 \
        path\cf7 .\cf4 left
\f2\b (
\f1\b0 \cf9 90
\f2\b \cf4 )
\f1\b0 \
\
    path\cf7 .\cf4 end_fill
\f2\b ()
\f1\b0 \
\

\f2\b \cf5 def
\f1\b0 \cf4  offset
\f2\b (
\f1\b0 point
\f2\b ):
\f1\b0 \
    \cf8 "Return offset of point in tiles."\cf4 \
    x \cf7 =\cf4  
\f2\b (
\f1\b0 floor
\f2\b (
\f1\b0 point\cf7 .\cf4 x
\f2\b ,
\f1\b0  \cf9 20
\f2\b \cf4 )
\f1\b0  \cf7 +\cf4  \cf9 200
\f2\b \cf4 )
\f1\b0  \cf7 /\cf4  \cf9 20\cf4 \
    y \cf7 =\cf4  
\f2\b (
\f1\b0 \cf9 180\cf4  \cf7 -\cf4  floor
\f2\b (
\f1\b0 point\cf7 .\cf4 y
\f2\b ,
\f1\b0  \cf9 20
\f2\b \cf4 ))
\f1\b0  \cf7 /\cf4  \cf9 20\cf4 \
    index \cf7 =\cf4  \cf5 int
\f2\b \cf4 (
\f1\b0 x \cf7 +\cf4  y \cf7 *\cf4  \cf9 20
\f2\b \cf4 )
\f1\b0 \
    
\f2\b \cf5 return
\f1\b0 \cf4  index\
\

\f2\b \cf5 def
\f1\b0 \cf4  valid
\f2\b (
\f1\b0 point
\f2\b ):
\f1\b0 \
    \cf8 "Return True if point is valid in tiles."\cf4 \
    index \cf7 =\cf4  offset
\f2\b (
\f1\b0 point
\f2\b )
\f1\b0 \
\
    
\f2\b \cf5 if
\f1\b0 \cf4  tiles
\f2\b [
\f1\b0 index
\f2\b ]
\f1\b0  \cf7 ==\cf4  \cf9 0
\f2\b \cf4 :
\f1\b0 \
        
\f2\b \cf5 return
\f1\b0 \cf4  
\f2\b \cf5 False
\f1\b0 \cf4 \
\
    index \cf7 =\cf4  offset
\f2\b (
\f1\b0 point \cf7 +\cf4  \cf9 19
\f2\b \cf4 )
\f1\b0 \
\
    
\f2\b \cf5 if
\f1\b0 \cf4  tiles
\f2\b [
\f1\b0 index
\f2\b ]
\f1\b0  \cf7 ==\cf4  \cf9 0
\f2\b \cf4 :
\f1\b0 \
        
\f2\b \cf5 return
\f1\b0 \cf4  
\f2\b \cf5 False
\f1\b0 \cf4 \
\
    
\f2\b \cf5 return
\f1\b0 \cf4  point\cf7 .\cf4 x \cf7 %\cf4  \cf9 20\cf4  \cf7 ==\cf4  \cf9 0\cf4  
\f2\b \cf5 or
\f1\b0 \cf4  point\cf7 .\cf4 y \cf7 %\cf4  \cf9 20\cf4  \cf7 ==\cf4  \cf9 0\cf4 \
\

\f2\b \cf5 def
\f1\b0 \cf4  world
\f2\b ():
\f1\b0 \
    \cf8 "Draw world using path."\cf4 \
    bgcolor
\f2\b (
\f1\b0 \cf8 'black'
\f2\b \cf4 )
\f1\b0 \
    path\cf7 .\cf4 color
\f2\b (
\f1\b0 \cf8 'blue'
\f2\b \cf4 )
\f1\b0 \
\
    
\f2\b \cf5 for
\f1\b0 \cf4  index 
\f2\b \cf5 in
\f1\b0 \cf4  \cf5 range
\f2\b \cf4 (
\f1\b0 \cf5 len
\f2\b \cf4 (
\f1\b0 tiles
\f2\b )):
\f1\b0 \
        tile \cf7 =\cf4  tiles
\f2\b [
\f1\b0 index
\f2\b ]
\f1\b0 \
\
        
\f2\b \cf5 if
\f1\b0 \cf4  tile \cf7 >\cf4  \cf9 0
\f2\b \cf4 :
\f1\b0 \
            x \cf7 =\cf4  
\f2\b (
\f1\b0 index \cf7 %\cf4  \cf9 20
\f2\b \cf4 )
\f1\b0  \cf7 *\cf4  \cf9 20\cf4  \cf7 -\cf4  \cf9 200\cf4 \
            y \cf7 =\cf4  \cf9 180\cf4  \cf7 -\cf4  
\f2\b (
\f1\b0 index \cf7 //\cf4  \cf9 20
\f2\b \cf4 )
\f1\b0  \cf7 *\cf4  \cf9 20\cf4 \
            square
\f2\b (
\f1\b0 x
\f2\b ,
\f1\b0  y
\f2\b )
\f1\b0 \
\
            
\f2\b \cf5 if
\f1\b0 \cf4  tile \cf7 ==\cf4  \cf9 1
\f2\b \cf4 :
\f1\b0 \
                path\cf7 .\cf4 up
\f2\b ()
\f1\b0 \
                path\cf7 .\cf4 goto
\f2\b (
\f1\b0 x \cf7 +\cf4  \cf9 10
\f2\b \cf4 ,
\f1\b0  y \cf7 +\cf4  \cf9 10
\f2\b \cf4 )
\f1\b0 \
                path\cf7 .\cf4 dot
\f2\b (
\f1\b0 \cf9 2
\f2\b \cf4 ,
\f1\b0  \cf8 'white'
\f2\b \cf4 )
\f1\b0 \
\

\f2\b \cf5 def
\f1\b0 \cf4  move
\f2\b ():
\f1\b0 \
    \cf8 "Move pacman and all ghosts."\cf4 \
    writer\cf7 .\cf4 undo
\f2\b ()
\f1\b0 \
    writer\cf7 .\cf4 write
\f2\b (
\f1\b0 state
\f2\b [
\f1\b0 \cf8 'score'
\f2\b \cf4 ])
\f1\b0 \
\
    clear
\f2\b ()
\f1\b0 \
\
    
\f2\b \cf5 if
\f1\b0 \cf4  valid
\f2\b (
\f1\b0 pacman \cf7 +\cf4  aim
\f2\b ):
\f1\b0 \
        pacman\cf7 .\cf4 move
\f2\b (
\f1\b0 aim
\f2\b )
\f1\b0 \
\
    index \cf7 =\cf4  offset
\f2\b (
\f1\b0 pacman
\f2\b )
\f1\b0 \
\
    
\f2\b \cf5 if
\f1\b0 \cf4  tiles
\f2\b [
\f1\b0 index
\f2\b ]
\f1\b0  \cf7 ==\cf4  \cf9 1
\f2\b \cf4 :
\f1\b0 \
        tiles
\f2\b [
\f1\b0 index
\f2\b ]
\f1\b0  \cf7 =\cf4  \cf9 2\cf4 \
        state
\f2\b [
\f1\b0 \cf8 'score'
\f2\b \cf4 ]
\f1\b0  \cf7 +=\cf4  \cf9 1\cf4 \
        x \cf7 =\cf4  
\f2\b (
\f1\b0 index \cf7 %\cf4  \cf9 20
\f2\b \cf4 )
\f1\b0  \cf7 *\cf4  \cf9 20\cf4  \cf7 -\cf4  \cf9 200\cf4 \
        y \cf7 =\cf4  \cf9 180\cf4  \cf7 -\cf4  
\f2\b (
\f1\b0 index \cf7 //\cf4  \cf9 20
\f2\b \cf4 )
\f1\b0  \cf7 *\cf4  \cf9 20\cf4 \
        square
\f2\b (
\f1\b0 x
\f2\b ,
\f1\b0  y
\f2\b )
\f1\b0 \
\
    up
\f2\b ()
\f1\b0 \
    goto
\f2\b (
\f1\b0 pacman\cf7 .\cf4 x \cf7 +\cf4  \cf9 10
\f2\b \cf4 ,
\f1\b0  pacman\cf7 .\cf4 y \cf7 +\cf4  \cf9 10
\f2\b \cf4 )
\f1\b0 \
    dot
\f2\b (
\f1\b0 \cf9 20
\f2\b \cf4 ,
\f1\b0  \cf8 'yellow'
\f2\b \cf4 )
\f1\b0 \
\
    
\f2\b \cf5 for
\f1\b0 \cf4  point
\f2\b ,
\f1\b0  course 
å\f2\b \cf5 in
\f1\b0 \cf4  ghosts
\f2\b :
\f1\b0 \
        
\f2\b \cf5 if
\f1\b0 \cf4  valid
\f2\b (
\f1\b0 point \cf7 +\cf4  course
\f2\b ):
\f1\b0 \
            point\cf7 .\cf4 move
\f2\b (
\f1\b0 course
\f2\b )
\f1\b0 \
        
\f2\b \cf5 else\cf4 :
\f1\b0 \
            options \cf7 =\cf4  
\f2\b [
\f1\b0 \
                vector
\f2\b (
\f1\b0 \cf9 5
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ),
\f1\b0 \
                vector
\f2\b (
\f1\b0 \cf7 -\cf9 5
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ),
\f1\b0 \
                vector
\f2\b (
\f1\b0 \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 5
\f2\b \cf4 ),
\f1\b0 \
                vector
\f2\b (
\f1\b0 \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf7 -\cf9 5
\f2\b \cf4 ),
\f1\b0 \
            
\f2\b ]
\f1\b0 \
            plan \cf7 =\cf4  choice
\f2\b (
\f1\b0 options
\f2\b )
\f1\b0 \
            course\cf7 .\cf4 x \cf7 =\cf4  plan\cf7 .\cf4 x\
            course\cf7 .\cf4 y \cf7 =\cf4  plan\cf7 .\cf4 y\
\
        up
\f2\b ()
\f1\b0 \
        goto
\f2\b (
\f1\b0 point\cf7 .\cf4 x \cf7 +\cf4  \cf9 10
\f2\b \cf4 ,
\f1\b0  point\cf7 .\cf4 y \cf7 +\cf4  \cf9 10
\f2\b \cf4 )
\f1\b0 \
        dot
\f2\b (
\f1\b0 \cf9 20
\f2\b \cf4 ,
\f1\b0  \cf8 'red'
\f2\b \cf4 )
\f1\b0 \
\
    update
\f2\b ()
\f1\b0 \
\
    
\f2\b \cf5 for
\f1\b0 \cf4  point
\f2\b ,
\f1\b0  course 
\f2\b \cf5 in
\f1\b0 \cf4  ghosts
\f2\b :
\f1\b0 \
        
\f2\b \cf5 if
\f1\b0 \cf4  \cf5 abs
\f2\b \cf4 (
\f1\b0 pacman \cf7 -\cf4  point
\f2\b )
\f1\b0  \cf7 <\cf4  \cf9 20
\f2\b \cf4 :
\f1\b0 \
            
\f2\b \cf5 return
\f1\b0 \cf4 \
\
    ontimer
\f2\b (
\f1\b0 move
\f2\b ,
\f1\b0  \cf9 100
\f2\b \cf4 )
\f1\b0 \
\

\f2\b \cf5 def
\f1\b0 \cf4  change
\f2\b (
\f1\b0 x
\f2\b ,
\f1\b0  y
\f2\b ):
\f1\b0 \
    \cf8 "Change pacman aim if valid."\cf4 \
    
\f2\b \cf5 if
\f1\b0 \cf4  valid
\f2\b (
\f1\b0 pacman \cf7 +\cf4  vector
\f2\b (
\f1\b0 x
\f2\b ,
\f1\b0  y
\f2\b )):
\f1\b0 \
        aim\cf7 .\cf4 x \cf7 =\cf4  x\
        aim\cf7 .\cf4 y \cf7 =\cf4  y\
\
setup
\f2\b (
\f1\b0 \cf9 420
\f2\b \cf4 ,
\f1\b0  \cf9 420
\f2\b \cf4 ,
\f1\b0  \cf9 370
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 )
\f1\b0 \
hideturtle
\f2\b ()
\f1\b0 \
tracer
\f2\b (\cf5 False\cf4 )
\f1\b0 \
writer\cf7 .\cf4 goto
\f2\b (
\f1\b0 \cf9 160
\f2\b \cf4 ,
\f1\b0  \cf9 160
\f2\b \cf4 )
\f1\b0 \
writer\cf7 .\cf4 color
\f2\b (
\f1\b0 \cf8 'white'
\f2\b \cf4 )
\f1\b0 \
writer\cf7 .\cf4 write
\f2\b (
\f1\b0 state
\f2\b [
\f1\b0 \cf8 'score'
\f2\b \cf4 ])
\f1\b0 \
listen
\f2\b ()
\f1\b0 \
onkey
\f2\b (\cf5 lambda\cf4 :
\f1\b0  change
\f2\b (
\f1\b0 \cf9 5
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ),
\f1\b0  \cf8 'Right'
\f2\b \cf4 )
\f1\b0 \
onkey
\f2\b (\cf5 lambda\cf4 :
\f1\b0  change
\f2\b (
\f1\b0 \cf7 -\cf9 5
\f2\b \cf4 ,
\f1\b0  \cf9 0
\f2\b \cf4 ),
\f1\b0  \cf8 'Left'
\f2\b \cf4 )
\f1\b0 \
onkey
\f2\b (\cf5 lambda\cf4 :
\f1\b0  change
\f2\b (
\f1\b0 \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf9 5
\f2\b \cf4 ),
\f1\b0  \cf8 'Up'
\f2\b \cf4 )
\f1\b0 \
onkey
\f2\b (\cf5 lambda\cf4 :
\f1\b0  change
\f2\b (
\f1\b0 \cf9 0
\f2\b \cf4 ,
\f1\b0  \cf7 -\cf9 5
\f2\b \cf4 ),
\f1\b0  \cf8 'Down'
\f2\b \cf4 )
\f1\b0 \
world
\f2\b ()
\f1\b0 \
move
\f2\b ()
\f1\b0 \
done
\f2\b ()}

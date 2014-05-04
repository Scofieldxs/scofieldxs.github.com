---
layout: post
title: java 内部类
cover: cover_1.jpg
date:   2014-05-04 12:00:00
categories: posts
---
<br/>
<br/>

java:内部类
===
##匿名内部类应用于工厂

	interface Game{boolean move();}
	interface GameFactory{Game getGame();}

	class Chess implements Game{
	private Chess(){}
	private int move=0;
	private static final int MOVES=4;
	public boolean move(){
		System.out.println("Chess moves"+move);
		return ++move==MOVES;
	}
	
	public static GameFactory fatoryFactory=new GameFactory() {//匿名内部类
		
		@Override
		public Game getGame() {
			// TODO Auto-generated method stub
			return new Chess();
		}
	};
	
	}

	public class Games {
	public static void playGame(GameFactory factory){
		Game s=factory.getGame();
		while(s.move());
	}
	public static void main(String[] args){
		playGame(Chess.fatoryFactory);
	}
	}****、


##Why 使用内部类
---
每个内部类都能独立继承自一个实现，等于变相多重继承
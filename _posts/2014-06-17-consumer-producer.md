---
layout: post
title: 多线程：生产者，消费者模型
cover: cover_5.jpg
date:   2014-06-17 12:00:00
categories: posts
---
<br/>
<br/>

多线程：生产者，消费者模型


	public class ProCon {
		public static void main(String[] args){
			SynStack stack=new SynStack();
			Consumer consumer=new Consumer(stack);
			Producer producer=new Producer(stack);
			
			new Thread(producer).start();
			new Thread(consumer).start();
		}
	}
	
	
	class SynStack{//表示仓库
		private String[] str=new String[10];
		private int index=-1;
		
		public synchronized void push(String a){
			if(index==str.length-1){
				try{
					wait();
				}catch(InterruptedException e){
					e.printStackTrace();
				}
			}
			this.notify();
			str[++index]=a;
		}
		
		public synchronized String pop(){
			if(index==-1){
				try{
					wait();				
				}catch(InterruptedException e){
					e.printStackTrace();
				}
			}
			notify();
			return str[index--];
		}
		
	}
	
	class Producer implements Runnable{
		private SynStack stack;
		private int productId=0;
		public Producer(SynStack stack){
			this.stack=stack;
		}
		@Override
		public void run() {
			// TODO Auto-generated method stub
			for(int i=0;i<10;i++){
				stack.push("Product "+productId);
				System.out.println("producing"+productId);
				productId++;		
				try{
					Thread.sleep(200);
				}catch(InterruptedException e){
					e.printStackTrace();
				}
			}
		}
	}
	
	class Consumer implements Runnable{
	
		private SynStack stack;
		
		public Consumer(SynStack stack){
			this.stack=stack;
		}
		
		@Override
		public void run() {
			// TODO Auto-generated method stub
			for(int i=0;i<10;i++){
				String product=stack.pop();
				System.out.println("Consuming"+product);
				try{
					Thread.sleep(300);
				}catch(InterruptedException e){
					e.printStackTrace();
				}
			}
		}
		
	}

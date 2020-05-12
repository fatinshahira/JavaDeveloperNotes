# My exercises based on JavaDeveloperNotes on YouTube

# Java Thread | How to create threads (Hello World) - https://www.youtube.com/watch?v=FtjwRAYj9C4 

```java
package hellothread;

public class HelloThread extends Thread {

    @Override
    public void run(){
            System.out.println("Hello Thread" + Thread.currentThread().getName());
    }
    public static void main(String[] args) {
            System.out.println(Thread.currentThread().getName());
            System.out.println(Thread.currentThread().getId());
        
            HelloThread helloThread1 = new HelloThread();
            HelloThread helloThread2 = new HelloThread();
            helloThread1.start();
            helloThread2.start();

    }
    
}
```
![output hello thread](https://user-images.githubusercontent.com/55240830/81713118-0f47c600-94a8-11ea-9df0-7e666e881d85.png)

# Java Thread | How to create threads by implementing Runnable Interface - https://www.youtube.com/watch?v=HMv5zszl40c

```java
package myrunnable;


public class MyRunnable implements Runnable{
    
    @Override
    public void run(){
        System.out.println(Thread.currentThread().getName());
    }
    
    
    public static void main(String[] args) {
       MyRunnable myRunnable = new MyRunnable();
       Thread t1 = new Thread(myRunnable);
       Thread t2 = new Thread(myRunnable);
       Thread t3 = new Thread(myRunnable);
       t1.start();
       t2.start();
       t3.start();
     //t3.start();    a thread can never be started again
    }
    
}
```


# Java Swing (GUI) | JProgressBar Example with Thread - https://www.youtube.com/watch?v=99EBmXUxRRk
```java
package progressbar1;

import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JOptionPane;
import javax.swing.JProgressBar;


public class ProgressBar1 {

     private final JFrame mainFrame;
     private final JButton startButton;
     private final JProgressBar progressBar;
     private Task task;
     
   public ProgressBar1(){
       mainFrame = new JFrame(" Progress Bar Example");
       mainFrame.setSize(600,400);
       mainFrame.setLayout(null);
       mainFrame.setDefaultCloseOperation(3);
       
       startButton = new JButton("Start");
       startButton.setBounds(50,50,100,50);
       startButton.addActionListener(new ActionListener() {
           
           @Override
           public void actionPerformed(ActionEvent e){
               task = new Task();
               task.start();
          // JOptionPane.showMessageDialog(null, "Finish");
   }
 
       });    
       
       progressBar = new JProgressBar(0, 100);
       progressBar.setBounds(50, 150, 500, 50);
       progressBar.setStringPainted(true);
       
       mainFrame.add(progressBar);
       mainFrame.add(startButton);
       mainFrame.setVisible(true);
}
    
    public static void main(String[] args) {
      new ProgressBar1();
         
    }

private class Task extends Thread{

    @Override
    public void run(){
        for (int i =0; i<= 100; i ++){
            progressBar.setValue(i);
            try{
               Thread.sleep(100);
            }catch (InterruptedException e){
                //e.printStackTrace();
            }
        }
        }
    }
}
```
![progress bar](https://user-images.githubusercontent.com/55240830/81713724-d0fed680-94a8-11ea-8a91-5b1f3e69f3e7.png)

# Java Thread | How to create threads by implementing Runnable Interface - https://www.youtube.com/watch?v=HMv5zszl40c
```java
package myrunnable;


public class MyRunnable implements Runnable{
    
    @Override
    public void run(){
        System.out.println(Thread.currentThread().getName());
    }
    
    
    public static void main(String[] args) {
       MyRunnable myRunnable = new MyRunnable();
       Thread t1 = new Thread(myRunnable);
       Thread t2 = new Thread(myRunnable);
       Thread t3 = new Thread(myRunnable);
       t1.start();
       t2.start();
       t3.start();
     //t3.start();    a thread can never be started again
    }
    
}
```
![myrunnable](https://user-images.githubusercontent.com/55240830/81716042-7f0b8000-94ab-11ea-849c-1ddd1d82baf4.png)


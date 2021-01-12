```java
//global variables
public class lab1{
    int num=0,count=0;


//main part
public static void Guessclick(){
    if(TextBox1.Text!=null&&Integer.parseInt(TextBox1.Text)>=1&&Integer.parseInt(TextBox1.Text)<=100){
        ++count;
        lab_counter.setText("You've tried"+count+"turns!");
        if(TextBox1.Text==num){
            showInfo.setText("Congratulations! You got the answer!");
            btn_guess.Enabled = false;
        }else if(TextBox1.Text<num){
            showInfo.setText("Try bigger number!");
        }else if(TextBox1.Text>num){
            showInfo.setText("Try smaller number!");
        }
    }
    if
}
private static void restart(){
    num=math.random(1,100);
    count=0
    lab_info.setText = "Enter a number between 1 and 100"
    lab_counter.setText("");
    TextBox1.setText("");
    btn_guess.Enabled = true;

}

private static void quit(){
    close_application();

}
}
```



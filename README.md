
package project;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.geometry.Insets;
import javafx.geometry.Pos;
import javafx.scene.Scene;
import javafx.scene.control.Alert;
import javafx.scene.control.Alert.AlertType;
import javafx.scene.control.Button;
import javafx.scene.control.Label;
import javafx.scene.control.PasswordField;
import javafx.scene.control.TextField;
import javafx.scene.layout.Background;
import javafx.scene.layout.BackgroundFill;
import javafx.scene.layout.GridPane;
import javafx.scene.paint.Color;
import javafx.scene.text.Font;
import javafx.scene.text.FontPosture;
import javafx.scene.text.FontWeight;
import javafx.stage.Stage;
public class Hotel extends Application {

	public static void main(String[] args) {
		
launch(args);
	}
	

	@Override
	public void start(Stage stage) throws Exception {
		stage.setTitle("     Admin  ");
		stage.setHeight(800);
		stage.setWidth(800);
		stage.setFullScreen(true);
		stage.setResizable(false);
		addComponent();
		stage.setScene(s);
		stage.show();
	}
	Scene s;
	private void addComponent()
	{
		
		Label admin=new Label("Admin");
		admin.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 70));
	    admin.setTextFill(Color.BLUE);
		
		Label u=new Label("username");
		TextField t=new  TextField();
		t.setBackground(new Background(new BackgroundFill(Color.ANTIQUEWHITE, null, null)));
        u.setFont(Font.font("Arial", FontWeight.EXTRA_BOLD	, FontPosture.REGULAR, 20));
		
		
		Label u1=new Label("Pasword");
		PasswordField y=new  PasswordField();
		u1.setFont(Font.font("Arial", FontWeight.EXTRA_BOLD	, FontPosture.REGULAR, 20));
		y.setBackground(new Background(new BackgroundFill(Color.ANTIQUEWHITE, null, null)));
		
		
		Button n=new Button("login");
		//Button n1=new Button("Signup");
		Button n2=new Button("Exit");
		
		n.setMinSize(130, 20);
		n2.setMinSize(130, 20);
		
		GridPane g=new GridPane();
		g.setAlignment(Pos.BASELINE_LEFT);
	
	    g.setStyle("-fx-background-image:url("+"'file:///D:/JAVA/hotel/src/hotel/images%20(1).jpg'"+");"+"-fx-background-size:cover;");
		g.setVgap(20);
		g.setHgap(20);
		g.add(admin	, 0, 0);
		g.add(u,0,1);
		g.add(t,0,1);
		g.setMargin(t, new Insets(0, 0, 0, 150));
		
		g.add(u1, 0,2);
		g.add(y,0,2);
		g.setMargin(y, new Insets(0, 0, 0, 150));
		
		g.add(n,0,3);
		//g.add(n1, 1 ,3);
		g.add(n2, 0 ,3);
		g.setMargin(n2, new Insets(0, 0, 0, 150));
		
		s=new Scene(g);
	n.setOnAction(new EventHandler<ActionEvent>() {
		
		@Override
		public void handle(ActionEvent event) {
			
			String nam,pas;
			pas=y.getText();
			nam=t.getText();
			
			if(nam.equals("Syed")&&pas.equals("1234"))
			{
				n.setOnAction(new EventHandler<ActionEvent>() {
					
					@Override
					public void handle(ActionEvent event) {
				
						MainWindow n=new MainWindow();
					}
				});
			}
			
			else
			{
		Alert a1=new Alert(AlertType.ERROR);
		a1.setHeaderText("INFO");
		a1.setContentText("LOGIN ERROR");
		a1.show();}
		}
	});
	
	
     n2.setOnAction(new EventHandler<ActionEvent>() {
		
		@Override
		public void handle(ActionEvent event) {
			System.exit(1);
		}
	});
	}
}
package project;

import javafx.scene.Scene;
import javafx.scene.control.Label;
import javafx.scene.control.ListView;
import javafx.scene.layout.VBox;
import javafx.stage.Stage;

public class Showdata {

	Stage stage;
	Scene scene;
	String data;
	
	public Showdata(String data) {
		this.data = data;
		stage = new Stage();
		stage.setTitle("Show Data");
		stage.setWidth(600);
		stage.setHeight(600);
		
		addcomponent();
		stage.setScene(scene);
		
		stage.show();
	
	}

	private void addcomponent() {
		
		VBox v = new VBox(10);
		
		Label head = new Label("Student Data");
		
		ListView<String> datalist = new ListView<String>();
		datalist.getItems().add(data);
		
		v.getChildren().addAll(head, datalist);
		
		scene = new Scene(v);
		
		
		
	}
}

package project;


import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;


 
public class connection {
	
	static String filename="data.txt";
	static void writetoFile(String data) throws IOException {
		FileWriter write=new FileWriter(filename,true);
			BufferedWriter writer=new BufferedWriter(write);
			writer.write(data);
			writer.newLine();
			writer.close();
			
	}
	public static void main(String[] args) {
		
	}

}

package project;

import java.io.IOException;

import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.geometry.Pos;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.control.Label;
import javafx.scene.control.TextField;
import javafx.scene.layout.Background;
import javafx.scene.layout.BackgroundFill;
import javafx.scene.layout.GridPane;
import javafx.scene.paint.Color;
import javafx.scene.text.Font;
import javafx.scene.text.FontPosture;
import javafx.scene.text.FontWeight;
import javafx.stage.Stage;

public class Signup {

	Stage stage;
	Scene scene,scene1 ;
	
	Signup(){
		
		
		stage= new Stage();
		stage.setTitle("Signup Screen");
		stage.setWidth(700);
		stage.setHeight(700);
		
		addcomponent();
		stage.setScene(scene);
		stage.show();
		
	}
		
	
	private void addcomponent(){
		Label n1= new Label("Cusomer Id");
		TextField t1 = new TextField();
		Label n2= new Label("Customer Name");
		TextField t2 = new TextField();
		Label n3= new Label("Address");
		TextField t3 = new TextField();
		Label n4= new Label("Phone No");
		TextField t4 = new TextField();
		Label n5= new Label("CNIC No");
		TextField t5 = new TextField();
		Label n6= new Label("Date of Birth");
		TextField t6 = new TextField();
		n1.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 20));
		n2.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 20));
		n3.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 20));
		n4.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 20));
		n5.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 20));
		n6.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 20));
	
		Button s7=new Button("Submit");
		Button s8=new Button("Exit");
		Button s9=new Button("Back to main menu");
		
		GridPane grid = new GridPane();
		grid.setAlignment(Pos.BASELINE_CENTER);
		grid.setVgap(20);
		grid.setHgap(20);
		
		grid.add(n1, 0, 0);
		grid.add(t1, 0, 1);
		grid.add(n2, 0, 2);
		grid.add(t2, 0, 3);
		grid.add(n3, 0, 4);
		grid.add(t3, 0, 5);
		grid.add(n4, 0, 6);
		grid.add(t4, 0, 7);
		grid.add(n5, 0, 8);
		grid.add(t5, 0, 9);
		grid.add(n6, 0, 10);
		grid.add(t6, 0, 11);
		grid.add(s7, 0, 12);
		grid.add(s8, 1, 12);
		grid.add(s9, 2, 12);
		
		grid.setBackground(new Background(new BackgroundFill(Color.IVORY, null, null)));
		
		
		scene = new Scene(grid);
		
		s7.setOnAction(new EventHandler<ActionEvent>() {

			@Override
			public void handle(ActionEvent event) {
				// TODO Auto-generated method stub
				
				
					// TODO Auto-generated method stub
					String detail=""; 
					
					detail+=n1.getText()+":";
					detail+=t1.getText() +"\n";
					
					detail+=n2.getText()+":";
					detail+=t2.getText()+"\n";
					
					detail+=n3.getText()+":";
					detail+=t3.getText()+"\n";
					
					detail+=n4.getText()+":";
					detail+=t4.getText()+"\n";
					
					detail+=n5.getText()+":";
					detail+=t5.getText()+"\n";
					
					detail+=n6.getText()+":";
					detail+=t6.getText()+"\n";
					Showdata sd = new Showdata(detail);
					/*detail+=regno.getText()+":";
					detail+=regnoF.getText()+"\n";
					
					detail+=dept.getText()+":";
					detail+=deptF.getText()+"\n";
					
					detail+=religion.getText()+":";
					if (r1.isSelected()) {
						reli="Islam";
					}
					if (r2.isSelected()) {
						reli="Hinduism";
					}
					if (r3.isSelected()) {
						reli="Other";
					}
					detail+=reli+=" \n";
					
					detail+=gender.getText()+":";
					if (male.isSelected()) {
						gen="male";
					}
					if (fmale.isSelected()) {
						gen="female";
					}
					if (other.isSelected()) {
						gen="Other";
					}*/
					//detail+=gen+=" \n";
					
//					System.out.println(detail);
					try {
						connection.writetoFile(detail);
						
					} catch (IOException e) {
						// TODO Auto-generated catch block
						e.printStackTrace();
					}
				
			}
			});

		s8.setOnAction(new EventHandler<ActionEvent>() {

			@Override
			public void handle(ActionEvent event) {
				// TODO Auto-generated method stub
				System.exit(1);
			}
		
	});
		s9.setOnAction(new EventHandler<ActionEvent>() {

			@Override
			public void handle(ActionEvent event) {
				// TODO Auto-generated method stub
				MainWindow n=new MainWindow();
			}
		
	});
	}

}


package project;

import java.io.IOException;

import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.geometry.Pos;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.control.Label;
import javafx.scene.control.TextField;
import javafx.scene.layout.Background;
import javafx.scene.layout.BackgroundFill;
import javafx.scene.layout.GridPane;
import javafx.scene.paint.Color;
import javafx.scene.text.Font;
import javafx.scene.text.FontPosture;
import javafx.scene.text.FontWeight;
import javafx.stage.Stage;


public class bthree {

	Stage stage;
	Scene scene,scene1 ;
	
	bthree(){
		
		stage= new Stage();
		stage.setTitle("Signup Screen");
		stage.setWidth(700);
		stage.setHeight(700);
		
		addcomponent();
		stage.setScene(scene);
		stage.show();
		
	}
		
	
	private void addcomponent(){
		Label n= new Label("Room Details");
		Label n1= new Label("Customer ID");
		TextField t1 = new TextField();
		Label n2= new Label("Customer Name");
		TextField t2 = new TextField();
		Label n3= new Label("Room Type");
		TextField t3 = new TextField();
		Label n4= new Label("Room Charges");
		TextField t4 = new TextField();
		Label n5= new Label("Total Room Reserved");
		TextField t5 = new TextField();
		Label n6= new Label("Room NO");
		TextField t6 = new TextField();
		Label n7= new Label("Time of stay");
		TextField t7 = new TextField();
		//Label n8= new Label("Time of stay");
		//TextField t8 = new TextField();
		n.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 25));
		n1.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 15));
		n2.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 15));
		n3.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 15));
		n4.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 15));
		n5.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 15));
		n6.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 15));
		n7.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 15));
		//n8.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 15));
		Button a=new Button("Submit");
		Button a1=new Button("Exit");
		Button a2=new Button("Back to main menu");
		
	
		
		GridPane grid = new GridPane();
		grid.setAlignment(Pos.CENTER);
		grid.setVgap(20);
		grid.setHgap(20);
		grid.add(n, 0, 0);
		grid.add(n1, 0, 1);
		grid.add(t1, 1, 1);
		grid.add(n2, 0, 2);
		grid.add(t2, 1, 2);
		grid.add(n3, 0, 3);
		grid.add(t3, 1, 3);
		grid.add(n4, 0, 4);
		grid.add(t4, 1, 4);
		grid.add(n5, 0, 5);
		grid.add(t5, 1, 5);
		grid.add(n6, 0, 6);
		grid.add(t6, 1, 6);
		grid.add(n7, 0, 7);
		grid.add(t7, 1, 7);
		//grid.add(n8, 0, 8);
		//grid.add(t8, 1, 8);
		grid.add(a, 0, 9);
		grid.add(a1, 1, 9);
		grid.add(a2, 2, 9);
		//grid.setMargin(a, new Insets(0,	 0,0,150));
		//grid.setMargin(a1, new Insets(0, 0, 0, 150));
		grid.setBackground(new Background(new BackgroundFill(Color.IVORY, null, null)));
		
		
		scene = new Scene(grid);
		a.setOnAction(new EventHandler<ActionEvent>() {

			@Override
			public void handle(ActionEvent event) {
				// TODO Auto-generated method stub

				String detail=""; 
				
				detail+=n1.getText()+":";
				detail+=t1.getText() +"\n";
				
				detail+=n2.getText()+":";
				detail+=t2.getText()+"\n";
				
				detail+=n3.getText()+":";
				detail+=t3.getText()+"\n";
				
				detail+=n4.getText()+":";
				detail+=t4.getText()+"\n";
				
				detail+=n5.getText()+":";
				detail+=t5.getText()+"\n";
				
				detail+=n6.getText()+":";
				detail+=t6.getText()+"\n";
				
				detail+=n7.getText()+":";
				detail+=t7.getText()+"\n";
				
				//detail+=n8.getText()+":";
				//detail+=t8.getText()+"\n";
				
				//ShowData sd = new ShowData(detail);
				
			   /*detail+=religion.getText()+":";
				if (r1.isSelected()) {
					reli="Islam";
				}
				if (r2.isSelected()) {
					reli="Hinduism";
				}
				if (r3.isSelected()) {
					reli="Other";
				}
				detail+=reli+=" \n";
				
				detail+=gender.getText()+":";
				if (male.isSelected()) {
					gen="male";
				}
				if (fmale.isSelected()) {
					gen="female";
				}
				if (other.isSelected()) {
					gen="Other";
				}
				detail+=gen+=" \n";
				*/
				System.out.println(detail);
				try {
					connection.writetoFile(detail);
					
				} catch (IOException e) {
					// TODO Auto-generated catch block
					e.printStackTrace();
				}
			}	
			
			});
		
		
		a1.setOnAction(new EventHandler<ActionEvent>() {

			@Override
			public void handle(ActionEvent event) {
				// TODO Auto-generated method stub
				System.exit(1);
			}
		
	});
		a2.setOnAction(new EventHandler<ActionEvent>() {

			@Override
			public void handle(ActionEvent event) {
				// TODO Auto-generated method stub
				MainWindow n=new MainWindow();
			}
		
	});
	
}
}

package project;

import java.io.IOException;

import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.geometry.Pos;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.control.Label;
import javafx.scene.control.TextField;
import javafx.scene.layout.Background;
import javafx.scene.layout.BackgroundFill;
import javafx.scene.layout.GridPane;
import javafx.scene.paint.Color;
import javafx.scene.text.Font;
import javafx.scene.text.FontPosture;
import javafx.scene.text.FontWeight;
import javafx.stage.Stage;


public class bfour {

	Stage stage;
	Scene scene,scene1 ;
	
	bfour(){
		
		stage= new Stage();
		stage.setTitle("Signup Screen");
		stage.setWidth(700);
		stage.setHeight(700);
		
		addcomponent();
		stage.setScene(scene);
		stage.show();
		
	}
		
	
	private void addcomponent(){
		Label n= new Label("Room Service");
		Label n1= new Label("Customer ID");
		TextField t1 = new TextField();
		Label n2= new Label("Customer Name");
		TextField t2 = new TextField();
		Label n3= new Label("Room no");
		TextField t3 = new TextField();
		Label n4= new Label("Food Order");
		TextField t4 = new TextField();
		Label n5= new Label("Beverages");
		TextField t5 = new TextField();
		Label n6= new Label("Others");
		TextField t6 = new TextField();
		//Label n7= new Label("Time of stay");
		//TextField t7 = new TextField();
		//Label n8= new Label("Time of stay");
		TextField t8 = new TextField();
		n.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 25));
		n1.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 15));
		n2.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 15));
		n3.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 15));
		n4.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 15));
		n5.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 15));
		n6.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 15));
		//n7.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 15));
		//n8.setFont(Font.font("Arial",FontWeight.EXTRA_BOLD, FontPosture.REGULAR, 15));
		Button a=new Button("Submit");
		Button a1=new Button("Exit");
		Button a2=new Button("Back to main menu");
		
	
		
		GridPane grid = new GridPane();
		grid.setAlignment(Pos.CENTER);
		grid.setVgap(20);
		grid.setHgap(20);
		grid.add(n, 0, 0);
		grid.add(n1, 0, 1);
		grid.add(t1, 1, 1);
		grid.add(n2, 0, 2);
		grid.add(t2, 1, 2);
		grid.add(n3, 0, 3);
		grid.add(t3, 1, 3);
		grid.add(n4, 0, 4);
		grid.add(t4, 1, 4);
		grid.add(n5, 0, 5);
		grid.add(t5, 1, 5);
		grid.add(n6, 0, 6);
		grid.add(t6, 1, 6);
	//	grid.add(n7, 0, 7);
	//	grid.add(t7, 1, 7);
		//grid.add(n8, 0, 8);
		//grid.add(t8, 1, 8);
		grid.add(a, 0, 9);
		grid.add(a1, 1, 9);
		grid.add(a2, 2, 9);
		//grid.setMargin(a, new Insets(0,	 0,0,150));
		//grid.setMargin(a1, new Insets(0, 0, 0, 150));
		grid.setBackground(new Background(new BackgroundFill(Color.IVORY, null, null)));
		
		
		scene = new Scene(grid);
		a.setOnAction(new EventHandler<ActionEvent>() {

			@Override
			public void handle(ActionEvent event) {
				// TODO Auto-generated method stub

				String detail=""; 
				
				detail+=n1.getText()+":";
				detail+=t1.getText() +"\n";
				
				detail+=n2.getText()+":";
				detail+=t2.getText()+"\n";
				
				detail+=n3.getText()+":";
				detail+=t3.getText()+"\n";
				
				detail+=n4.getText()+":";
				detail+=t4.getText()+"\n";
				
				detail+=n5.getText()+":";
				detail+=t5.getText()+"\n";
				
				detail+=n6.getText()+":";
				detail+=t6.getText()+"\n";
				
			//	detail+=n7.getText()+":";
				//detail+=t7.getText()+"\n";
				
				//detail+=n8.getText()+":";
				//detail+=t8.getText()+"\n";
				
				Showdata sd = new Showdata(detail);
				
			   /*detail+=religion.getText()+":";
				if (r1.isSelected()) {
					reli="Islam";
				}
				if (r2.isSelected()) {
					reli="Hinduism";
				}
				if (r3.isSelected()) {
					reli="Other";
				}
				detail+=reli+=" \n";
				
				detail+=gender.getText()+":";
				if (male.isSelected()) {
					gen="male";
				}
				if (fmale.isSelected()) {
					gen="female";
				}
				if (other.isSelected()) {
					gen="Other";
				}
				detail+=gen+=" \n";
				*/
				System.out.println(detail);
				try {
					connection.writetoFile(detail);
					
				} catch (IOException e) {
					// TODO Auto-generated catch block
					e.printStackTrace();
				}
			}	
			
			});
		
		
		a1.setOnAction(new EventHandler<ActionEvent>() {

			@Override
			public void handle(ActionEvent event) {
				// TODO Auto-generated method stub
				System.exit(1);
			}
		
	});
		a2.setOnAction(new EventHandler<ActionEvent>() {

			@Override
			public void handle(ActionEvent event) {
				// TODO Auto-generated method stub
				MainWindow n=new MainWindow();
			}
		
	});

	
	
}}

package project;

import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.HBox;
import javafx.stage.Stage;
import project.bthree;

public class MainWindow {

	
	Stage stage;
	Scene scene ;
	
  MainWindow(){
	  
	  stage= new Stage();
		stage.setTitle("login screen");
		stage.setWidth(200);
		stage.setHeight(200);
		stage.setFullScreen(true);
		addcomponent();
		stage.setScene(scene);
		stage.show();
  }
 

	public void addcomponent(){
		
		Button b1 = new Button("1");
		Button b2 = new Button("2");
		Button b3 = new Button("3");
		Button b4 = new Button("4");
		Button b5 = new Button("5");
		
		b1.setMinSize(200, 100);
		b2.setMinSize(200, 100);
		b3.setMinSize(200, 100);
		b4.setMinSize(200, 100);
		
		HBox hboox = new HBox(190);
		hboox.getChildren().addAll(b1, b2, b3, b4);
		scene = new Scene(hboox);
		
		b2.setOnAction(new EventHandler<ActionEvent>() {

			@Override
			public void handle(ActionEvent event) {
				// TODO Auto-generated method stub
				Signup b2 =new Signup();
			}
			
			
		});
	
		b3.setOnAction(new EventHandler<ActionEvent>() {

			@Override
			public void handle(ActionEvent event) {
				// TODO Auto-generated method stub
			
				bthree b3=new bthree();
			}
			
		});
		
		b4.setOnAction(new EventHandler<ActionEvent>() {

			@Override
			public void handle(ActionEvent event) {
				// TODO Auto-generated method stub
			
				bfour b4=new bfour();
			}
			
		});
	/*	b5.setOnAction(new EventHandler<ActionEvent>() {

			@Override
			public void handle(ActionEvent event) {
				// TODO Auto-generated method stub
			
				ShowData sd = new ShowData(detail);
			}
			
		});
		*/
}}

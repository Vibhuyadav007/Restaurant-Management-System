#include<bits/stdc++.h>
using namespace std;

// table-> table no, no of seats,reserved(bool),reservation_name(bool)
// intialise table->table no, no of seats
//reserve the table
// cancel reservation
// return string representation of table

class restaurant{
	
	class table{
	
	private :
		
		int table_no;
		int seats;
		bool reserved=0;
		string person="";
        
	public:
		
	void setTable(int table_no,int seats){
		this->table_no=table_no;
		this->seats=seats;
	}
		
	void reserveTable(string name){
		if(this->reserved){
			cout<<"Sorry !! Already reserved"<<endl;
			return;
		}
		this->reserved=1;
		this->person=name;
		cout<<"You reserved this  table successfully"<<endl;
	}
	
	void cancelReservation(){
		if(!this->reserved){
			cout<<"You didn't have reserved this table"<<endl;
			return;
		}
		this->reserved=0;
		this->person="";
		cout<<"You cancel reservation of the table"<<endl;
	}
	
	string owner(){
		if(this->reserved){
			return this->person;
		}
		else
		return "Not reserved yet";
	}
	
	
	// Getters
	
	int getSeats(){
		return seats;
	}
	
	int getReserveStatus(){
		return reserved;
	} 
	string getOwner(){
		return person;
	} 
	
	void table_details(){
		cout<<table_no<<" "<<seats<<endl;
	}
	
};

	private:
		map<int,table> tb;
	public:
		void addTable(){
			int table_no;
			cout<<"Enter the table number to be added."<<endl;
			cin>>table_no;
			if(tb.count(table_no)==0){
				int no_seats;
				cout<<"Enter number of seats"<<endl;
				cin>>no_seats;
				table t;
				t.setTable(table_no,no_seats);
				tb[table_no]=t;
			}
			else 
			cout<<"Table already existed"<<endl;	
		}
		
		void removeTable(){
			int table_no;
			cout<<"Enter the table number to remove"<<endl;
			cin>>table_no;
			if(tb.count(table_no)){
				tb.erase(table_no);
				cout<<"Table Number "<<table_no <<" is successfully removed."<<endl;
				
			}
			else 
			cout<<"Table doesn't existed"<<endl;	
		}
		
		void findTable(){
			cout<<"Enter the table number to find"<<endl;
			int table_no;
			cin>>table_no;
			if(tb.count(table_no)){
				cout<<"Table number of table is "<<table_no<<endl;
				cout<<"Number of seats in a table is "<<tb[table_no].getSeats()<<endl;
				if(tb[table_no].getReserveStatus()){
					cout<<"The table is reserved by "<<tb[table_no].getOwner()<<endl;
				}
				else{
					cout<<"This table is not reserved"<<endl;
				}
			}
            else{
                cout<<"There is no such table"<<endl;
            }
		}
		
		void checkAvailableTables(){
			vector<int> temp;
			for(auto it:tb){
				if(it.second.getReserveStatus()==0)
				temp.push_back(it.first);
			}
			if(temp.size()>0){
				cout<<"The available tables are as follows : "<<endl;
				for(auto x:temp)
				cout<<x<<" ";
				cout<<endl;
			}
			else{
				cout<<"All the tables are reserved"<<endl;
			}
		}
		
		void resTable(){
            cout<<"Enter the table number you want to reserve "<<endl;
            int table_no;
            cin>>table_no;
            if(tb.count(table_no)){
                cout<<"Enter your name"<<endl;
                string newuser;
                cin>>newuser;
                tb[table_no].reserveTable(newuser);

            }
            else{
                cout<<"There is no such table"<<endl;
            }
        }

        void cancelTable(){
            cout<<"Enter the table number you want to cancel"<<endl;
            int table_no;
            cin>>table_no;
            if(tb.count(table_no)==0){
                cout<<"Please mention right table number";
            }
            else{
                tb[table_no].cancelReservation();
                return;
            }
        }
		
	
};

int main(){
//	table a;
//	a.setTable(1,10);
//	a.table_details();
//	a.reserveTable("Ram");
//	a.cancelReservation();
//	a.reserveTable("x");
//  cout<<a.owner();

    // restaurant r;
    // r.addTable();
// r.resTable();
// r.resTable();
// r.cancelTable();
restaurant r;
int tc;
bool flag=true;
cout<<"Your options are :"<<endl;
cout<<"Press 1 : Add a table"<<endl;
cout<<"Press 2 : Remove a table"<<endl;
cout<<"Press 3 : Find a table"<<endl;
cout<<"Press 4 : Find available tables"<<endl;
cout<<"Press 5 : Reserve a table"<<endl;
cout<<"Press 6 : Cancel reservation "<<endl;
cout<<"Choose your options"<<endl;


while(flag){
    cin>>tc;
    switch(tc){
        case 1:
        r.addTable();
        break;
        case 2:
        r.removeTable();
        break;
        case 3:
        r.findTable();
        break;
        case 4:
        r.checkAvailableTables();
        break;
        case 5:
        r.resTable();
        break;
        case 6:
        r.cancelTable();
        break;
        default:{
            flag=0;
        }
    }
}

	return 0;
}

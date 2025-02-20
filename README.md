# JDDC-CRUD-Operation
CRUD stands for Create, Read, Update, and Delete, which are the four essential operations for managing data in a database. Below is a breakdown of how these operations are performed using Java and MySQL (JDBC)
1. Create (Insert Data)
Adds new records into the database.
Uses INSERT INTO SQL statement.
Executed using Statement.executeUpdate().
Example Code:

java
Copy
Edit
public static void insertData() throws SQLException {
    String url = "jdbc:mysql://localhost:3306/new_schema";
    String userName = "root";
    String password = "yourpassword";
    String query = "INSERT INTO employees VALUES (1, 'Arun', 'Kumar', '1988-06-10')";
    
    Connection con = DriverManager.getConnection(url, userName, password);
    Statement st = con.createStatement();
    int rows = st.executeUpdate(query);
    
    System.out.println(rows + " row(s) inserted.");
    con.close();
}
2. Read (Retrieve Data)
Fetches data from the database.
Uses SELECT * FROM SQL statement.
Executed using Statement.executeQuery().
Example Code:

java
Copy
Edit
public static void viewData() throws SQLException {
    String url = "jdbc:mysql://localhost:3306/new_schema";
    String userName = "root";
    String password = "yourpassword";
    String query = "SELECT * FROM employees";

    Connection con = DriverManager.getConnection(url, userName, password);
    Statement st = con.createStatement();
    ResultSet rs = st.executeQuery(query);

    while (rs.next()) {
        System.out.println("ID: " + rs.getInt(1));
        System.out.println("FIRST NAME: " + rs.getString(2));
        System.out.println("LAST NAME: " + rs.getString(3));
        System.out.println("DATE: " + rs.getString(4));
    }
    con.close();
}
3. Update (Modify Data)
Modifies existing records.
Uses UPDATE SQL statement.
Executed using Statement.executeUpdate().
Example Code:

java
Copy
Edit
public static void updateData() throws SQLException {
    String url = "jdbc:mysql://localhost:3306/new_schema";
    String userName = "root";
    String password = "yourpassword";
    String query = "UPDATE employees SET last_name = 'Susa' WHERE employee_id = 1";

    Connection con = DriverManager.getConnection(url, userName, password);
    Statement st = con.createStatement();
    int rows = st.executeUpdate(query);

    System.out.println(rows + " row(s) updated.");
    con.close();
}
4. Delete (Remove Data)
Deletes records from the database.
Uses DELETE FROM SQL statement.
Executed using Statement.executeUpdate().
Example Code:

java
Copy
Edit
public static void deleteData() throws SQLException {
    String url = "jdbc:mysql://localhost:3306/new_schema";
    String userName = "root";
    String password = "yourpassword";
    String query = "DELETE FROM employees WHERE employee_id = 1";

    Connection con = DriverManager.getConnection(url, userName, password);
    Statement st = con.createStatement();
    int rows = st.executeUpdate(query);

    System.out.println(rows + " row(s) deleted.");
    con.close();
}
Conclusion
Create → INSERT INTO
Read → SELECT
Update → UPDATE
Delete → DELETE
These operations allow full control over the database using Java and JDBC. You can improve security and efficiency by using PreparedStatement instead of Statement. 🚀

Let me know if you need any modifications! 😊

# Zoo Monitoring Project

# Overview
The Zoo Monitoring Project is a Java-based application originally developed to track zoo animals and their habitats. This enhancement aims to improve the design and functionality of the program by adding several key features, including a login system, employee records management, and the transition from text file reading to SQL Server database connectivity.

Features
# Login System:

Verifies user credentials.
Retrieves the user's access level to determine the menu options available.
Employee Records Management:

Allows HR and admin personnel to retrieve and manage employee records.
Stores details such as name, hire date, position, salary, and habitats maintained by zookeepers.
# Main Menu:

Simplified and streamlined for better usability.
Displays options based on the user's access level.
SQL Server Database Connectivity:

Replaces the previous text file reading method.
Ensures secure and efficient data management.
Enhancements

# Refactored Main Method:
Original method was overly complex.
New method is streamlined, focusing on login verification and menu navigation.
Switch Statement in Main Menu:
Controls access based on user levels to protect personal information and ensure job-level access.
Future Enhancements

# Graphical User Interface (GUI):
A potential future enhancement to improve user experience.

# Advanced Access Levels:
Different levels of access for zookeepers and HR personnel based on responsibilities.
Additional functions for adding, updating, and deleting records, with a "deleted" flag for maintaining accurate records.

Code Example
# SQL Logic in Login Class Using JDBC:

public boolean login(String username, String password) {
    try {
        Connection conn = DriverManager.getConnection(dbUrl, dbUsername, dbPassword);
        String sql = "SELECT * FROM Users WHERE username = ? AND password = ?";
        PreparedStatement pstmt = conn.prepareStatement(sql);
        pstmt.setString(1, username);
        pstmt.setString(2, password);
        ResultSet rs = pstmt.executeQuery();
        
        if (rs.next()) {
            this.username = username;
            this.accessLevel = rs.getString("accessLevel");
            return true;
        }
    } catch (SQLException e) {
        e.printStackTrace();
    }
    return false;
}

Installation
# Prerequisites:

Java Development Kit (JDK)
SQL Server
JDBC Driver for SQL Server

# Setup:
Clone the repository from GitHub.
Configure the database connection settings in the project.
Import the project into your preferred Java IDE.
Run the project.

# Repository
The entire project can be found on GitHub: Zoo Monitoring Project GitHub Repository

# Contribution
Feel free to fork the repository and contribute to future enhancements. Please submit pull requests for any improvements or bug fixes.

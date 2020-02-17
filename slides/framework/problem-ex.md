## JEE not focused on business

```java
public class JdbcPersonService {
    public Person findByLogin(String login) {
        Connection con;
        PreparedStatement stmt;
        ResultSet rs = null;
        try {
            String sql = "select * from PERSON where LOGIN = ?";
            con = DriverManager.getConnection("localhost:3306/person");
            stmt = con.prepareStatement(sql);
            stmt.setString(1, login);
            rs = stmt.executeQuery();
            if (rs.next()) {
                Person person = new Person();
                person.setLogin(rs.getNString(1));
                person.setFirstName(rs.getNString(2));
                person.setLastName(rs.getNString(3));
                return person;
            } else {
                return null;
            }
        } catch (SQLException e) {
            e.printStackTrace();
        } finally {
            try {
                if (rs != null && !rs.isClosed()) {
                    rs.close();
                }
            } catch (Exception e) {
                //Here I'm totally screwed
            }
        }
        return null;
    }
}

```

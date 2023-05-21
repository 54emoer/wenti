package Test;
import pojo.Course;
import utils.MyBatisUtils;
import org.apache.ibatis.session.SqlSession;
import org.junit.Test;
import java.util.List;
public class mybatisTest {
    //查询计算机学院所有的课程信息
    @Test
    public void insertNewTest(){
        SqlSession session=MyBatisUtils.getSession();
        Course course=new Course();
        course.setId(5);
        course.setName("大数据存储");
        course.setHours(32);
        course.setSid(1);
        int row= session.insert("mapper"+".courseMapper.insertNew",course);
        if(row>0)
        {
            System.out.println("您成功插入"+row+"条数据");
        }else{
            System.out.println("插入失败");
        }
        session.close();
    }

}

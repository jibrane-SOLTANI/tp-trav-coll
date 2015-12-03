import java.util.Properties;

import javax.naming.Context;
import javax.naming.InitialContext;
import javax.naming.NamingException;

import EjbSession.IHotelRemote;
import Package_Metier.Hotel;


public class Test {

	public static void main(String[] args) {

		Properties prop=new Properties();
		prop.put(Context.URL_PKG_PREFIXES,"org.jboss.ejb.client.naming");

		Context cntxt=new InitialContext(prop);

		IHotelRemote InstInt=(IHotelRemote)cntxt.lookup("ejb:/PROJET_Gestion_Hotel/ImpInRem!EjbSession.IHotelRemote");
/*		
		Hotel hot=new Hotel("africa",(short) 5);

		InstInt.AjouterHotel(hot);
*/
		
		for(int i=0;i<InstInt.ConsulterListeHotel().size();i++){
			System.out.println(InstInt.ConsulterListeHotel().get(i).getID_Hotel());
		}
		
}
}

}

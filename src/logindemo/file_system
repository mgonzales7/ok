
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package logindemo;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
import java.io.Reader;
import java.util.ArrayList;
import java.util.List;
import java.io.File;
import java.util.Arrays;
import org.apache.commons.csv.*;
public class file_system {
	private static final String NEW_LINE_SEPARATOR = "\n";
	public static void update_file(String fileName, String[] HEADERS, String[][] data)
	{
		FileWriter fileWriter = null;
		CSVPrinter csvFilePrinter = null;
		CSVFormat csvFileFormat = CSVFormat.DEFAULT.withRecordSeparator(NEW_LINE_SEPARATOR);
		try {
	            //initialize FileWriter object
	            fileWriter = new FileWriter(fileName);
	            //initialize CSVPrinter object
	            csvFilePrinter = new CSVPrinter(fileWriter, csvFileFormat);
	            //Create CSV file header
	            csvFilePrinter.printRecord(HEADERS);
	            for(int i = 0; i < data.length; i++)
	            {
                            csvFilePrinter.printRecord(data[i]); 
	            }
                }
		catch(Exception e){System.out.println(e);}
		finally
		{
			try{
				fileWriter.flush();
				fileWriter.close();
				csvFilePrinter.close();
			}catch(IOException e){System.out.println(e);}
			
		}
	}
	public static ArrayList<ArrayList<String>> read_from_file(String fileName,String[] headers)
	{		
            ArrayList<ArrayList<String>> data =  new ArrayList<ArrayList<String>>();
            CSVFormat csvFileFormat = CSVFormat.DEFAULT.withHeader(headers);
            CSVParser csvFileParser = null;
            try
            {
                Reader in = new FileReader(fileName);
                csvFileParser = new CSVParser(in,csvFileFormat);
                Iterable<CSVRecord> records = csvFileParser.getRecords();
                int row_count = 0;
                for(CSVRecord record: records)
                {
                    data.add(new ArrayList<String>());
                    for(String row:record)
                    {
                        data.get(row_count).add(row);
                    }
                    row_count++;
                }
            }catch(Exception e)
            {
                    System.out.println(e);
            }
            return data;
	}
        public static void create_file(String fileName)
        {
            File newFile = new File(fileName);
        }
        public static boolean check_existance(String fileName)
        {
            if(new File(fileName).exists()) 
               return true;
            else    
               return false;
        }
}
        


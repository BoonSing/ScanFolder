# ScanFolder
Scan your PC folder

import java.io.File;
import java.util.Arrays;

public class ScanFolder 
{

	public static void main (String [] args)
	{
		
		String path = "C:/";

		File folder = new File(path);		
		File [] listOfFile = folder.listFiles();
		
		final int MAX = listOfFile.length;
		String [] file = new String [MAX];
		String [] directory = new String [MAX];
		
		int fileCount = 0, directoryCount = 0;
		
		int j = 0;
		
		for (int i = 0 ; i <= (MAX - 1); i++)
		{
			//Store if it is folder
			if (listOfFile[i].isDirectory())
			{
				directory[i] = listOfFile[i].getName();
				directoryCount ++;
			}
			
			//Store if it is file
			if (listOfFile[i].isFile())
			{
				file[j] = listOfFile[i].getName();
				fileCount ++;
				j ++;
			}
		}
		
		System.out.println ("List of directory: " + "(" + directoryCount + ")");
		for (int x = 0 ; x < MAX ; x ++)
		{
			if (directory[x] != null)
			{
				System.out.println (directory[x]);
			}
			
		}
		System.out.println ();
		System.out.println ("List of file: " + "(" + fileCount + ")");
		
		for (int x = 0 ; x < MAX ; x ++)
		{
			if (file[x] != null)
			{
				System.out.println (file[x]);
			}
			
		}
		   
	}
}

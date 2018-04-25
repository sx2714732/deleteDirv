package com.siebel.www.xml.HWEmpSplitIO.holders.test;

import java.io.File;
public class deleteDirv
{

                private deleteDirv()
                {
                }
                
                public static void main(String[] args)
                {
                    long t1 = System.currentTimeMillis();
                    String folder = "D:\\project2\\workspace(1.27)";
                    if (null != args && args.length > 0)
                    {
                        folder = args[0];
                    }
                    delete(folder);
                    System.out.println((System.currentTimeMillis()-t1)/1000);
                }
                
                public static void delete(String folderName)
                {
                    if (null == folderName || folderName.isEmpty())
                    {
                        return;
                    }
                    try
                    {
                        File folder = new File(folderName);
                        delete(folder);
                    }
                    catch (Exception ex)
                    {
                        ex.printStackTrace();
                    }
                }
                
                public static void delete(File folder)
                {
                    try
                    {
                        if (!folder.isDirectory())
                        {
                            System.out.println("Delete file : " + folder.getAbsolutePath());
                            folder.delete();
                        }
                        else
                        {
                            for (File file : folder.listFiles())
                            {
                                delete(file);
                            }
                            System.out.println("Delete folder for :" + folder.getAbsolutePath());
                            folder.delete();
                        }
                    }
                    catch (Exception ex)
                    {
                        ex.printStackTrace();
                    }
                }
            
         
}

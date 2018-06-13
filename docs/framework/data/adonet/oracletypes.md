---
title: Tipos de Oracle
ms.date: 03/30/2017
ms.assetid: 18143304-d5c7-4c95-9995-678088d0c142
ms.openlocfilehash: c64f0d6788aea3663218c81ea6278eed826372f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356743"
---
# <a name="oracletypes"></a><span data-ttu-id="7e1e7-102">Tipos de Oracle</span><span class="sxs-lookup"><span data-stu-id="7e1e7-102">OracleTypes</span></span>
<span data-ttu-id="7e1e7-103">El proveedor de datos .NET Framework para Oracle incluye varias estructuras que se pueden utilizar para trabajar con tipos de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="7e1e7-103">The .NET Framework Data Provider for Oracle includes several structures you can use to work with Oracle data types.</span></span> <span data-ttu-id="7e1e7-104">Por ejemplo, <xref:System.Data.OracleClient.OracleNumber> y <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="7e1e7-104">These include <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e1e7-105">Para ver una lista completa de estas estructuras, vea <xref:System.Data.OracleClient>.</span><span class="sxs-lookup"><span data-stu-id="7e1e7-105">For a complete list of these structures, see <xref:System.Data.OracleClient>.</span></span>  
  
 <span data-ttu-id="7e1e7-106">En los siguientes ejemplos con C#:</span><span class="sxs-lookup"><span data-stu-id="7e1e7-106">The following C# examples:</span></span>  
  
-   <span data-ttu-id="7e1e7-107">se crea una tabla de Oracle y se carga de datos.</span><span class="sxs-lookup"><span data-stu-id="7e1e7-107">Create an Oracle table and load it with data.</span></span>  
  
-   <span data-ttu-id="7e1e7-108">se utiliza un <xref:System.Data.OracleClient.OracleDataReader> para tener acceso a los datos y se emplean varias estructuras <xref:System.Data.OracleClient.OracleType> para mostrarlos.</span><span class="sxs-lookup"><span data-stu-id="7e1e7-108">Use an <xref:System.Data.OracleClient.OracleDataReader> to access the data, and use several <xref:System.Data.OracleClient.OracleType> structures to display the data.</span></span>  
  
## <a name="creating-an-oracle-table"></a><span data-ttu-id="7e1e7-109">Creación de una tabla de Oracle</span><span class="sxs-lookup"><span data-stu-id="7e1e7-109">Creating an Oracle Table</span></span>  
 <span data-ttu-id="7e1e7-110">En este ejemplo se crea una tabla de Oracle y se carga de datos.</span><span class="sxs-lookup"><span data-stu-id="7e1e7-110">This example creates an Oracle table and loads it with data.</span></span> <span data-ttu-id="7e1e7-111">Este ejemplo debe ejecutarse antes que el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7e1e7-111">You must run this example before running the next example.</span></span>  
  
```csharp  
public void Setup(string connectionString)  
   {  
   OracleConnection conn = new OracleConnection(connectionString);  
   try  
      {  
      conn.Open();  
      OracleCommand cmd = conn.CreateCommand();  
      cmd.CommandText ="CREATE TABLE OracleTypesTable " +  
        "(MyVarchar2 varchar2(3000),MyNumber number(28,4) " +  
        "PRIMARY KEY ,MyDate date, MyRaw raw(255))";  
      cmd.ExecuteNonQuery();  
      cmd.CommandText ="INSERT INTO OracleTypesTable VALUES " +  
        "( 'test', 2, to_date('2000-01-11 12:54:01','yyyy-mm-dd " +  
        "hh24:mi:ss'), '0001020304' )";  
      cmd.ExecuteNonQuery();  
      }  
   catch(Exception)  
   {  
   }  
   finally  
   {  
      conn.Close();  
   }  
}  
```  
  
## <a name="retrieving-data-from-the-oracle-table"></a><span data-ttu-id="7e1e7-112">Recuperación de datos de la tabla de Oracle</span><span class="sxs-lookup"><span data-stu-id="7e1e7-112">Retrieving Data from the Oracle Table</span></span>  
 <span data-ttu-id="7e1e7-113">Este ejemplo se utiliza un **OracleDataReader** para tener acceso a los datos y se emplean varias **OracleType** estructuras para mostrar los datos.</span><span class="sxs-lookup"><span data-stu-id="7e1e7-113">This example uses an **OracleDataReader** to access the data, and uses several **OracleType** structures to display the data.</span></span>  
  
```csharp  
public void ReadOracleTypesExample(string connectionString)  
   {  
   OracleConnection myConnection =   
      new OracleConnection(connectionString);  
   myConnection.Open();  
   OracleCommand myCommand = myConnection.CreateCommand();  
  
   try  
      {  
      myCommand.CommandText = "SELECT * from OracleTypesTable";  
      OracleDataReader oracledatareader1 = myCommand.ExecuteReader();  
      oracledatareader1.Read();  
  
      //Using the oracle specific getters for each type is faster than  
      //using GetOracleValue.  
  
      //First column, MyVarchar2, is a VARCHAR2 data type in Oracle  
      //Server and maps to OracleString.  
      OracleString oraclestring1 =   
        oracledatareader1.GetOracleString(0);  
      Console.WriteLine("OracleString " + oraclestring1.ToString());  
  
      //Second column, MyNumber, is a NUMBER data type in Oracle Server  
      //and maps to OracleNumber.  
      OracleNumber oraclenumber1 =   
        oracledatareader1.GetOracleNumber(1);  
      Console.WriteLine("OracleNumber " + oraclenumber1.ToString());  
  
      //Third column, MyDate, is a DATA data type in Oracle Server  
      //and maps to OracleDateTime.  
      OracleDateTime oracledatetime1 =   
        oracledatareader1.GetOracleDateTime(2);  
      Console.WriteLine("OracleDateTime " + oracledatetime1.ToString());  
  
      //Fourth column, MyRaw, is a RAW data type in Oracle Server and  
      //maps to OracleBinary.  
      OracleBinary oraclebinary1 =   
        oracledatareader1.GetOracleBinary(3);  
      //Calling value on a null OracleBinary throws  
      //OracleNullValueException; therefore, check for a null value.  
      if (oraclebinary1.IsNull==false)  
      {  
         foreach(byte b in oraclebinary1.Value)  
         {  
            Console.WriteLine("byte " + b.ToString());  
         }  
      }  
      oracledatareader1.Close();  
   }  
   catch(Exception e)  
   {  
       Console.WriteLine(e.ToString());  
   }  
   finally  
   {  
       myConnection.Close();  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e1e7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e1e7-114">See Also</span></span>  
 [<span data-ttu-id="7e1e7-115">Oracle y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7e1e7-115">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="7e1e7-116">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="7e1e7-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

---
title: Objetos BFILE de Oracle
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 2d7db741cea5421b2391588c0479f44e2b478ca3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626424"
---
# <a name="oracle-bfiles"></a><span data-ttu-id="926bb-102">Objetos BFILE de Oracle</span><span class="sxs-lookup"><span data-stu-id="926bb-102">Oracle BFILEs</span></span>
<span data-ttu-id="926bb-103">El proveedor de datos .NET Framework para Oracle incluye la clase <xref:System.Data.OracleClient.OracleBFile>, que se utiliza para trabajar con el tipo de datos <xref:System.Data.OracleClient.OracleType.BFile> de Oracle.</span><span class="sxs-lookup"><span data-stu-id="926bb-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle <xref:System.Data.OracleClient.OracleType.BFile> data type.</span></span>  
  
 <span data-ttu-id="926bb-104">Oracle **BFILE** es de tipo de datos Oracle **LOB** tipo de datos que contiene una referencia a datos binarios con un tamaño máximo de 4 gigabytes.</span><span class="sxs-lookup"><span data-stu-id="926bb-104">The Oracle **BFILE** data type is an Oracle **LOB** data type that contains a reference to binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="926bb-105">Oracle **BFILE** difiere de otro Oracle **LOB** tipos de datos en que sus datos se almacenan en un archivo físico en el sistema operativo en lugar de en el servidor.</span><span class="sxs-lookup"><span data-stu-id="926bb-105">An Oracle **BFILE** differs from other Oracle **LOB** data types in that its data is stored in a physical file in the operating system instead of on the server.</span></span> <span data-ttu-id="926bb-106">Tenga en cuenta que el **BFILE** tipo de datos proporciona acceso de solo lectura a los datos.</span><span class="sxs-lookup"><span data-stu-id="926bb-106">Note that the **BFILE** data type provides read-only access to data.</span></span>  
  
 <span data-ttu-id="926bb-107">Otras características de un **BFILE** tipo de datos que lo distinguen de un **LOB** son que el tipo de datos:</span><span class="sxs-lookup"><span data-stu-id="926bb-107">Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span></span>  
  
- <span data-ttu-id="926bb-108">contiene datos no estructurados.</span><span class="sxs-lookup"><span data-stu-id="926bb-108">Contains unstructured data.</span></span>  
  
- <span data-ttu-id="926bb-109">admite el troceo en el servidor.</span><span class="sxs-lookup"><span data-stu-id="926bb-109">Supports server-side chunking.</span></span>  
  
- <span data-ttu-id="926bb-110">utiliza semántica de copia de referencia.</span><span class="sxs-lookup"><span data-stu-id="926bb-110">Uses reference copy semantics.</span></span> <span data-ttu-id="926bb-111">Por ejemplo, si realiza una operación de copia en un **BFILE**, solo el **BFILE** se copia el localizador (que es una referencia al archivo).</span><span class="sxs-lookup"><span data-stu-id="926bb-111">For example, if you perform a copy operation on a **BFILE**, only the **BFILE** locator (which is a reference to the file) is copied.</span></span> <span data-ttu-id="926bb-112">Los datos del archivo no se copian.</span><span class="sxs-lookup"><span data-stu-id="926bb-112">The data in the file is not copied.</span></span>  
  
 <span data-ttu-id="926bb-113">El **BFILE** se debe usar el tipo de datos para hacer referencia a los LOB que son de gran tamaño y por lo tanto, no es práctico almacenar en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="926bb-113">The **BFILE** data type should be used for referencing LOBs that are large in size, and therefore, not practical to store in the database.</span></span> <span data-ttu-id="926bb-114">Más sobrecarga de comunicación, el servidor y el cliente está implicada cuando se usa un **BFILE** tipo de datos en comparación con el **LOB** tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="926bb-114">More client, server, and communication overhead is involved when using a **BFILE** data type compared with the **LOB** data type.</span></span> <span data-ttu-id="926bb-115">Resulta más eficaz para tener acceso a un **BFILE** si sólo necesita obtener una pequeña cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="926bb-115">It is more efficient to access a **BFILE** if you only need to obtain a small amount of data.</span></span> <span data-ttu-id="926bb-116">En cambio, si necesita obtener el objeto entero, es más eficiente tener acceso a los LOB residentes en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="926bb-116">It is more efficient to access database-resident LOBs if you need to obtain the entire object.</span></span>  
  
 <span data-ttu-id="926bb-117">Cada distinto de NULL **OracleBFile** objeto está asociado con dos entidades que definen la ubicación del archivo físico subyacente:</span><span class="sxs-lookup"><span data-stu-id="926bb-117">Each non-NULL **OracleBFile** object is associated with two entities that define the location of the underlying physical file:</span></span>  
  
1. <span data-ttu-id="926bb-118">Un objeto DIRECTORY de Oracle, que es un alias de base de datos de un directorio del sistema de archivos, y</span><span class="sxs-lookup"><span data-stu-id="926bb-118">An Oracle DIRECTORY object, which is a database alias for a directory in the file system, and</span></span>  
  
2. <span data-ttu-id="926bb-119">el nombre de archivo del archivo físico subyacente, que se encuentra en el directorio asociado con el objeto DIRECTORY.</span><span class="sxs-lookup"><span data-stu-id="926bb-119">The file name of the underlying physical file, which is located in the directory associated with the DIRECTORY object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="926bb-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="926bb-120">Example</span></span>  
 <span data-ttu-id="926bb-121">En el ejemplo de C# siguiente se muestra cómo puede crear un **BFILE** en Oracle, tabla y, a continuación, recuperarlo en forma de un **OracleBFile** objeto.</span><span class="sxs-lookup"><span data-stu-id="926bb-121">The following C# example demonstrates how you can create a **BFILE** in an Oracle table and then retrieve it in the form of an **OracleBFile** object.</span></span> <span data-ttu-id="926bb-122">En el ejemplo se muestra cómo utilizar el <xref:System.Data.OracleClient.OracleDataReader> objeto y el **OracleBFile** **Seek** y **lectura** métodos.</span><span class="sxs-lookup"><span data-stu-id="926bb-122">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleBFile** **Seek** and **Read** methods.</span></span> <span data-ttu-id="926bb-123">Tenga en cuenta que para usar este ejemplo, primero debe crear un directorio denominado "c:\\\bfiles" y el archivo llamado "MyFile.jpg" en el servidor de Oracle.</span><span class="sxs-lookup"><span data-stu-id="926bb-123">Note that in order to use this sample, you must first create a directory named "c:\\\bfiles" and file named "MyFile.jpg" on the Oracle server.</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Data;  
using System.Data.OracleClient;  
  
public class Sample  
{  
   public static void Main(string[] args)  
   {  
      OracleConnection connection = new OracleConnection(  
        "Data Source=Oracle8i;Integrated Security=yes");  
      connection.Open();  
  
      OracleCommand command = connection.CreateCommand();  
      command.CommandText =   
        "CREATE or REPLACE DIRECTORY MyDir as 'c:\\bfiles'";  
      command.ExecuteNonQuery();  
      command.CommandText =   
        "DROP TABLE MyBFileTable";  
      try {  
        command.ExecuteNonQuery();  
      }  
      catch {  
      }  
      command.CommandText =   
        "CREATE TABLE MyBFileTable(col1 number, col2 BFILE)";  
      command.ExecuteNonQuery();  
      command.CommandText =   
        "INSERT INTO MyBFileTable values ('2', BFILENAME('MyDir', " +  
        "'MyFile.jpg'))";  
      command.ExecuteNonQuery();  
      command.CommandText = "SELECT * FROM MyBFileTable";  
  
        byte[] buffer = new byte[100];  
  
      OracleDataReader reader = command.ExecuteReader();  
      using (reader) {  
          if (reader.Read()) {  
                OracleBFile bFile = reader.GetOracleBFile(1);  
                using (bFile) {  
                  bFile.Seek(0, SeekOrigin.Begin);  
                  bFile.Read(buffer, 0, 100);  
              }  
          }  
      }  
  
      connection.Close();  
   }  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="926bb-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="926bb-124">See also</span></span>

- [<span data-ttu-id="926bb-125">Oracle y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="926bb-125">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [<span data-ttu-id="926bb-126">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="926bb-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

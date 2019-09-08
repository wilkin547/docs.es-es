---
title: Objetos BFILE de Oracle
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 214140bb8fcf43154b014ea3db609d355a27af7c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794635"
---
# <a name="oracle-bfiles"></a><span data-ttu-id="b14c3-102">Objetos BFILE de Oracle</span><span class="sxs-lookup"><span data-stu-id="b14c3-102">Oracle BFILEs</span></span>
<span data-ttu-id="b14c3-103">El proveedor de datos .NET Framework para Oracle incluye la clase <xref:System.Data.OracleClient.OracleBFile>, que se utiliza para trabajar con el tipo de datos <xref:System.Data.OracleClient.OracleType.BFile> de Oracle.</span><span class="sxs-lookup"><span data-stu-id="b14c3-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle <xref:System.Data.OracleClient.OracleType.BFile> data type.</span></span>  
  
 <span data-ttu-id="b14c3-104">El tipo de datos **BFILE** de Oracle es un tipo de datos **LOB** de Oracle que contiene una referencia a datos binarios con un tamaño máximo de 4 gigabytes.</span><span class="sxs-lookup"><span data-stu-id="b14c3-104">The Oracle **BFILE** data type is an Oracle **LOB** data type that contains a reference to binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="b14c3-105">Un **BFILE** de Oracle difiere de otros tipos de datos **LOB** de Oracle en que sus datos se almacenan en un archivo físico en el sistema operativo en lugar de en el servidor.</span><span class="sxs-lookup"><span data-stu-id="b14c3-105">An Oracle **BFILE** differs from other Oracle **LOB** data types in that its data is stored in a physical file in the operating system instead of on the server.</span></span> <span data-ttu-id="b14c3-106">Tenga en cuenta que el tipo de datos **BFILE** proporciona acceso de solo lectura a los datos.</span><span class="sxs-lookup"><span data-stu-id="b14c3-106">Note that the **BFILE** data type provides read-only access to data.</span></span>  
  
 <span data-ttu-id="b14c3-107">Otras características de un tipo de datos **BFILE** que lo diferencian de un tipo de datos **LOB** son que:</span><span class="sxs-lookup"><span data-stu-id="b14c3-107">Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span></span>  
  
- <span data-ttu-id="b14c3-108">contiene datos no estructurados.</span><span class="sxs-lookup"><span data-stu-id="b14c3-108">Contains unstructured data.</span></span>  
  
- <span data-ttu-id="b14c3-109">admite el troceo en el servidor.</span><span class="sxs-lookup"><span data-stu-id="b14c3-109">Supports server-side chunking.</span></span>  
  
- <span data-ttu-id="b14c3-110">utiliza semántica de copia de referencia.</span><span class="sxs-lookup"><span data-stu-id="b14c3-110">Uses reference copy semantics.</span></span> <span data-ttu-id="b14c3-111">Por ejemplo, si realiza una operación de copia en un **BFILE**, solo se copia el localizador **BFILE** (que es una referencia al archivo).</span><span class="sxs-lookup"><span data-stu-id="b14c3-111">For example, if you perform a copy operation on a **BFILE**, only the **BFILE** locator (which is a reference to the file) is copied.</span></span> <span data-ttu-id="b14c3-112">Los datos del archivo no se copian.</span><span class="sxs-lookup"><span data-stu-id="b14c3-112">The data in the file is not copied.</span></span>  
  
 <span data-ttu-id="b14c3-113">El tipo de datos **BFILE** debe usarse para hacer referencia a los LOB que tienen un tamaño grande y, por lo tanto, no resulta práctico almacenar en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b14c3-113">The **BFILE** data type should be used for referencing LOBs that are large in size, and therefore, not practical to store in the database.</span></span> <span data-ttu-id="b14c3-114">Si se usa un tipo de datos de **BFILE** en comparación con el tipo de datos **LOB** , se supone más sobrecarga de cliente, de servidor y de comunicación.</span><span class="sxs-lookup"><span data-stu-id="b14c3-114">More client, server, and communication overhead is involved when using a **BFILE** data type compared with the **LOB** data type.</span></span> <span data-ttu-id="b14c3-115">Es más eficaz acceder a un **BFILE** si solo necesita obtener una pequeña cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="b14c3-115">It is more efficient to access a **BFILE** if you only need to obtain a small amount of data.</span></span> <span data-ttu-id="b14c3-116">En cambio, si necesita obtener el objeto entero, es más eficiente tener acceso a los LOB residentes en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b14c3-116">It is more efficient to access database-resident LOBs if you need to obtain the entire object.</span></span>  
  
 <span data-ttu-id="b14c3-117">Cada objeto **OracleBFile** no NULL está asociado a dos entidades que definen la ubicación del archivo físico subyacente:</span><span class="sxs-lookup"><span data-stu-id="b14c3-117">Each non-NULL **OracleBFile** object is associated with two entities that define the location of the underlying physical file:</span></span>  
  
1. <span data-ttu-id="b14c3-118">Un objeto DIRECTORY de Oracle, que es un alias de base de datos de un directorio del sistema de archivos, y</span><span class="sxs-lookup"><span data-stu-id="b14c3-118">An Oracle DIRECTORY object, which is a database alias for a directory in the file system, and</span></span>  
  
2. <span data-ttu-id="b14c3-119">el nombre de archivo del archivo físico subyacente, que se encuentra en el directorio asociado con el objeto DIRECTORY.</span><span class="sxs-lookup"><span data-stu-id="b14c3-119">The file name of the underlying physical file, which is located in the directory associated with the DIRECTORY object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b14c3-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b14c3-120">Example</span></span>  
 <span data-ttu-id="b14c3-121">En el C# ejemplo siguiente se muestra cómo se puede crear un **BFILE** en una tabla de Oracle y, a continuación, recuperarlo en forma de un objeto **OracleBFile** .</span><span class="sxs-lookup"><span data-stu-id="b14c3-121">The following C# example demonstrates how you can create a **BFILE** in an Oracle table and then retrieve it in the form of an **OracleBFile** object.</span></span> <span data-ttu-id="b14c3-122">En el ejemplo se muestra <xref:System.Data.OracleClient.OracleDataReader> el uso del objeto y de los métodos **Seek** y **Read** de **OracleBFile** .</span><span class="sxs-lookup"><span data-stu-id="b14c3-122">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleBFile** **Seek** and **Read** methods.</span></span> <span data-ttu-id="b14c3-123">Tenga en cuenta que para poder usar este ejemplo, primero debe crear un directorio denominado "c:\\\bfiles" y un archivo denominado "archivo. jpg" en el servidor de Oracle.</span><span class="sxs-lookup"><span data-stu-id="b14c3-123">Note that in order to use this sample, you must first create a directory named "c:\\\bfiles" and file named "MyFile.jpg" on the Oracle server.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b14c3-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="b14c3-124">See also</span></span>

- [<span data-ttu-id="b14c3-125">Oracle y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b14c3-125">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="b14c3-126">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b14c3-126">ADO.NET Overview</span></span>](ado-net-overview.md)

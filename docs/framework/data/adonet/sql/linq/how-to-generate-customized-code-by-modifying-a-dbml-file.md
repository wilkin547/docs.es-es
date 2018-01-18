---
title: "Cómo: Generar código personalizado modificando un archivo DBML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c9a2b382c84548d3226fe68531961e0f53033e7d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a><span data-ttu-id="ea118-102">Cómo: Generar código personalizado modificando un archivo DBML</span><span class="sxs-lookup"><span data-stu-id="ea118-102">How to: Generate Customized Code by Modifying a DBML File</span></span>
<span data-ttu-id="ea118-103">Puede generar [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] o código fuente de C# desde un archivo de metadatos base de datos (.dbml) de lenguaje de marcado.</span><span class="sxs-lookup"><span data-stu-id="ea118-103">You can generate [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# source code from a database markup language (.dbml) metadata file.</span></span> <span data-ttu-id="ea118-104">Este enfoque proporciona una oportunidad de personalizar el archivo .dbml predeterminado antes de generar el código de asignación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ea118-104">This approach provides an opportunity to customize the default .dbml file before you generate the application mapping code.</span></span> <span data-ttu-id="ea118-105">Ésta es una característica avanzada.</span><span class="sxs-lookup"><span data-stu-id="ea118-105">This is an advanced feature.</span></span>  
  
 <span data-ttu-id="ea118-106">Los pasos de este proceso son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="ea118-106">The steps in this process are as follows:</span></span>  
  
1.  <span data-ttu-id="ea118-107">Genere un archivo .dbml.</span><span class="sxs-lookup"><span data-stu-id="ea118-107">Generate a .dbml file.</span></span>  
  
2.  <span data-ttu-id="ea118-108">Utilice un editor para modificar el archivo .dbml.</span><span class="sxs-lookup"><span data-stu-id="ea118-108">Use an editor to modify the .dbml file.</span></span> <span data-ttu-id="ea118-109">Tenga en cuenta que el archivo .dbml debe validarse con el archivo de esquema (.xsd) de definición para [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] archivos .dbml.</span><span class="sxs-lookup"><span data-stu-id="ea118-109">Note that the .dbml file must validate against the schema definition (.xsd) file for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml files.</span></span> <span data-ttu-id="ea118-110">Para obtener más información, consulte [generación de código en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ea118-110">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
3.  <span data-ttu-id="ea118-111">Genere el código fuente de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] o de C#.</span><span class="sxs-lookup"><span data-stu-id="ea118-111">Generate the [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# source code.</span></span>  
  
 <span data-ttu-id="ea118-112">En los ejemplos siguientes se utiliza la herramienta de línea de comandos SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="ea118-112">The following examples use the SQLMetal command-line tool.</span></span> <span data-ttu-id="ea118-113">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="ea118-113">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea118-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea118-114">Example</span></span>  
 <span data-ttu-id="ea118-115">El código siguiente genera un archivo .dbml a partir de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="ea118-115">The following code generates a .dbml file from the Northwind sample database.</span></span> <span data-ttu-id="ea118-116">Como origen de los metadatos de la base de datos, puede utilizar el nombre de la base de datos o el nombre del archivo .mdf.</span><span class="sxs-lookup"><span data-stu-id="ea118-116">As source for the database metadata, you can use either the name of the database or the name of the .mdf file.</span></span>  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a><span data-ttu-id="ea118-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea118-117">Example</span></span>  
 <span data-ttu-id="ea118-118">El código siguiente genera un archivo de código fuente de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] o C# a partir de un archivo .dbml.</span><span class="sxs-lookup"><span data-stu-id="ea118-118">The following code generates [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# source code file from a .dbml file.</span></span>  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea118-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea118-119">See Also</span></span>  
 [<span data-ttu-id="ea118-120">Generación de código en LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="ea118-120">Code Generation in LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [<span data-ttu-id="ea118-121">SqlMetal.exe (Herramienta de generación de código)</span><span class="sxs-lookup"><span data-stu-id="ea118-121">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [<span data-ttu-id="ea118-122">Creación del modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="ea118-122">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)

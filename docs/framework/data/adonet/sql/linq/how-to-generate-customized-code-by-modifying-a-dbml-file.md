---
title: Procedimiento para generar código personalizado mediante la modificación de un archivo DBML
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: ab49f76a0d5e7338a93e21ae9a8d1d9d74a21e82
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173444"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a><span data-ttu-id="e1aeb-102">Procedimiento para generar código personalizado mediante la modificación de un archivo DBML</span><span class="sxs-lookup"><span data-stu-id="e1aeb-102">How to: Generate Customized Code by Modifying a DBML File</span></span>

<span data-ttu-id="e1aeb-103">Puede generar Visual Basic o código fuente de C# a partir de un archivo de metadatos de lenguaje de marcado de base de datos (. dbml).</span><span class="sxs-lookup"><span data-stu-id="e1aeb-103">You can generate Visual Basic or C# source code from a database markup language (.dbml) metadata file.</span></span> <span data-ttu-id="e1aeb-104">Este enfoque proporciona una oportunidad de personalizar el archivo .dbml predeterminado antes de generar el código de asignación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e1aeb-104">This approach provides an opportunity to customize the default .dbml file before you generate the application mapping code.</span></span> <span data-ttu-id="e1aeb-105">Ésta es una característica avanzada.</span><span class="sxs-lookup"><span data-stu-id="e1aeb-105">This is an advanced feature.</span></span>  
  
 <span data-ttu-id="e1aeb-106">Los pasos de este proceso son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="e1aeb-106">The steps in this process are as follows:</span></span>  
  
1. <span data-ttu-id="e1aeb-107">Genere un archivo .dbml.</span><span class="sxs-lookup"><span data-stu-id="e1aeb-107">Generate a .dbml file.</span></span>  
  
2. <span data-ttu-id="e1aeb-108">Utilice un editor para modificar el archivo .dbml.</span><span class="sxs-lookup"><span data-stu-id="e1aeb-108">Use an editor to modify the .dbml file.</span></span> <span data-ttu-id="e1aeb-109">Tenga en cuenta que el archivo. dbml debe validarse con el archivo de definición de esquema (. xsd) para [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] los archivos. dbml.</span><span class="sxs-lookup"><span data-stu-id="e1aeb-109">Note that the .dbml file must validate against the schema definition (.xsd) file for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml files.</span></span> <span data-ttu-id="e1aeb-110">Para obtener más información, vea [generación de código en LINQ to SQL](code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="e1aeb-110">For more information, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md).</span></span>  
  
3. <span data-ttu-id="e1aeb-111">Generar el código fuente de Visual Basic o C#.</span><span class="sxs-lookup"><span data-stu-id="e1aeb-111">Generate the Visual Basic or C# source code.</span></span>  
  
 <span data-ttu-id="e1aeb-112">En los ejemplos siguientes se utiliza la herramienta de línea de comandos SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="e1aeb-112">The following examples use the SQLMetal command-line tool.</span></span> <span data-ttu-id="e1aeb-113">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="e1aeb-113">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1aeb-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1aeb-114">Example</span></span>  

 <span data-ttu-id="e1aeb-115">El código siguiente genera un archivo .dbml a partir de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="e1aeb-115">The following code generates a .dbml file from the Northwind sample database.</span></span> <span data-ttu-id="e1aeb-116">Como origen de los metadatos de la base de datos, puede utilizar el nombre de la base de datos o el nombre del archivo .mdf.</span><span class="sxs-lookup"><span data-stu-id="e1aeb-116">As source for the database metadata, you can use either the name of the database or the name of the .mdf file.</span></span>  
  
```console  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a><span data-ttu-id="e1aeb-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1aeb-117">Example</span></span>  

 <span data-ttu-id="e1aeb-118">El código siguiente genera Visual Basic o un archivo de código fuente de C# a partir de un archivo. dbml.</span><span class="sxs-lookup"><span data-stu-id="e1aeb-118">The following code generates Visual Basic or C# source code file from a .dbml file.</span></span>  
  
```console
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1aeb-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1aeb-119">See also</span></span>

- [<span data-ttu-id="e1aeb-120">Generación de código en LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e1aeb-120">Code Generation in LINQ to SQL</span></span>](code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="e1aeb-121">SqlMetal.exe (Herramienta de generación de código)</span><span class="sxs-lookup"><span data-stu-id="e1aeb-121">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [<span data-ttu-id="e1aeb-122">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="e1aeb-122">Creating the Object Model</span></span>](creating-the-object-model.md)

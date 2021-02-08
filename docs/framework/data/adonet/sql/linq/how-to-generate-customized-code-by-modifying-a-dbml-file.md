---
description: 'Más información sobre: Cómo: generar código personalizado modificando un archivo DBML'
title: Procedimiento para generar código personalizado mediante la modificación de un archivo DBML
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: 0dd4024b3f6a0ca0583de6bfbdb7463fab14d969
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786009"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a><span data-ttu-id="bed68-103">Procedimiento para generar código personalizado mediante la modificación de un archivo DBML</span><span class="sxs-lookup"><span data-stu-id="bed68-103">How to: Generate Customized Code by Modifying a DBML File</span></span>

<span data-ttu-id="bed68-104">Puede generar Visual Basic o código fuente de C# a partir de un archivo de metadatos de lenguaje de marcado de base de datos (. dbml).</span><span class="sxs-lookup"><span data-stu-id="bed68-104">You can generate Visual Basic or C# source code from a database markup language (.dbml) metadata file.</span></span> <span data-ttu-id="bed68-105">Este enfoque proporciona una oportunidad de personalizar el archivo .dbml predeterminado antes de generar el código de asignación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bed68-105">This approach provides an opportunity to customize the default .dbml file before you generate the application mapping code.</span></span> <span data-ttu-id="bed68-106">Ésta es una característica avanzada.</span><span class="sxs-lookup"><span data-stu-id="bed68-106">This is an advanced feature.</span></span>  
  
 <span data-ttu-id="bed68-107">Los pasos de este proceso son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="bed68-107">The steps in this process are as follows:</span></span>  
  
1. <span data-ttu-id="bed68-108">Genere un archivo .dbml.</span><span class="sxs-lookup"><span data-stu-id="bed68-108">Generate a .dbml file.</span></span>  
  
2. <span data-ttu-id="bed68-109">Utilice un editor para modificar el archivo .dbml.</span><span class="sxs-lookup"><span data-stu-id="bed68-109">Use an editor to modify the .dbml file.</span></span> <span data-ttu-id="bed68-110">Tenga en cuenta que el archivo. dbml debe validarse con el archivo de definición de esquema (. xsd) para [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] los archivos. dbml.</span><span class="sxs-lookup"><span data-stu-id="bed68-110">Note that the .dbml file must validate against the schema definition (.xsd) file for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml files.</span></span> <span data-ttu-id="bed68-111">Para obtener más información, vea [generación de código en LINQ to SQL](code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="bed68-111">For more information, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md).</span></span>  
  
3. <span data-ttu-id="bed68-112">Generar el código fuente de Visual Basic o C#.</span><span class="sxs-lookup"><span data-stu-id="bed68-112">Generate the Visual Basic or C# source code.</span></span>  
  
 <span data-ttu-id="bed68-113">En los ejemplos siguientes se utiliza la herramienta de línea de comandos SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="bed68-113">The following examples use the SQLMetal command-line tool.</span></span> <span data-ttu-id="bed68-114">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="bed68-114">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bed68-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bed68-115">Example</span></span>  

 <span data-ttu-id="bed68-116">El código siguiente genera un archivo .dbml a partir de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="bed68-116">The following code generates a .dbml file from the Northwind sample database.</span></span> <span data-ttu-id="bed68-117">Como origen de los metadatos de la base de datos, puede utilizar el nombre de la base de datos o el nombre del archivo .mdf.</span><span class="sxs-lookup"><span data-stu-id="bed68-117">As source for the database metadata, you can use either the name of the database or the name of the .mdf file.</span></span>  
  
```console  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a><span data-ttu-id="bed68-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bed68-118">Example</span></span>  

 <span data-ttu-id="bed68-119">El código siguiente genera Visual Basic o un archivo de código fuente de C# a partir de un archivo. dbml.</span><span class="sxs-lookup"><span data-stu-id="bed68-119">The following code generates Visual Basic or C# source code file from a .dbml file.</span></span>  
  
```console
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a><span data-ttu-id="bed68-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="bed68-120">See also</span></span>

- [<span data-ttu-id="bed68-121">Generación de código en LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="bed68-121">Code Generation in LINQ to SQL</span></span>](code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="bed68-122">SqlMetal.exe (Herramienta de generación de código)</span><span class="sxs-lookup"><span data-stu-id="bed68-122">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [<span data-ttu-id="bed68-123">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="bed68-123">Creating the Object Model</span></span>](creating-the-object-model.md)

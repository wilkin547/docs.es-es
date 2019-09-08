---
title: Procedimiento para generar código personalizado mediante la modificación de un archivo DBML
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: 01890e6b899db6b70049e2d6b8193e5b0f4095fb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781985"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a><span data-ttu-id="5062a-102">Procedimiento para generar código personalizado mediante la modificación de un archivo DBML</span><span class="sxs-lookup"><span data-stu-id="5062a-102">How to: Generate Customized Code by Modifying a DBML File</span></span>
<span data-ttu-id="5062a-103">Puede generar Visual Basic o C# código fuente a partir de un archivo de metadatos de lenguaje de marcado de base de datos (. dbml).</span><span class="sxs-lookup"><span data-stu-id="5062a-103">You can generate Visual Basic or C# source code from a database markup language (.dbml) metadata file.</span></span> <span data-ttu-id="5062a-104">Este enfoque proporciona una oportunidad de personalizar el archivo .dbml predeterminado antes de generar el código de asignación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5062a-104">This approach provides an opportunity to customize the default .dbml file before you generate the application mapping code.</span></span> <span data-ttu-id="5062a-105">Ésta es una característica avanzada.</span><span class="sxs-lookup"><span data-stu-id="5062a-105">This is an advanced feature.</span></span>  
  
 <span data-ttu-id="5062a-106">Los pasos de este proceso son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="5062a-106">The steps in this process are as follows:</span></span>  
  
1. <span data-ttu-id="5062a-107">Genere un archivo .dbml.</span><span class="sxs-lookup"><span data-stu-id="5062a-107">Generate a .dbml file.</span></span>  
  
2. <span data-ttu-id="5062a-108">Utilice un editor para modificar el archivo .dbml.</span><span class="sxs-lookup"><span data-stu-id="5062a-108">Use an editor to modify the .dbml file.</span></span> <span data-ttu-id="5062a-109">Tenga en cuenta que el archivo. dbml debe validarse con el archivo de definición de esquema [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (. xsd) para los archivos. dbml.</span><span class="sxs-lookup"><span data-stu-id="5062a-109">Note that the .dbml file must validate against the schema definition (.xsd) file for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml files.</span></span> <span data-ttu-id="5062a-110">Para obtener más información, vea [generación de código en LINQ to SQL](code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="5062a-110">For more information, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md).</span></span>  
  
3. <span data-ttu-id="5062a-111">Generar el Visual Basic o C# código fuente.</span><span class="sxs-lookup"><span data-stu-id="5062a-111">Generate the Visual Basic or C# source code.</span></span>  
  
 <span data-ttu-id="5062a-112">En los ejemplos siguientes se utiliza la herramienta de línea de comandos SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="5062a-112">The following examples use the SQLMetal command-line tool.</span></span> <span data-ttu-id="5062a-113">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="5062a-113">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5062a-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5062a-114">Example</span></span>  
 <span data-ttu-id="5062a-115">El código siguiente genera un archivo .dbml a partir de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="5062a-115">The following code generates a .dbml file from the Northwind sample database.</span></span> <span data-ttu-id="5062a-116">Como origen de los metadatos de la base de datos, puede utilizar el nombre de la base de datos o el nombre del archivo .mdf.</span><span class="sxs-lookup"><span data-stu-id="5062a-116">As source for the database metadata, you can use either the name of the database or the name of the .mdf file.</span></span>  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a><span data-ttu-id="5062a-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5062a-117">Example</span></span>  
 <span data-ttu-id="5062a-118">El código siguiente genera Visual Basic o C# un archivo de código fuente a partir de un archivo. dbml.</span><span class="sxs-lookup"><span data-stu-id="5062a-118">The following code generates Visual Basic or C# source code file from a .dbml file.</span></span>  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a><span data-ttu-id="5062a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5062a-119">See also</span></span>

- [<span data-ttu-id="5062a-120">Generación de código en LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5062a-120">Code Generation in LINQ to SQL</span></span>](code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="5062a-121">SqlMetal.exe (Herramienta de generación de código)</span><span class="sxs-lookup"><span data-stu-id="5062a-121">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [<span data-ttu-id="5062a-122">Creación del modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="5062a-122">Creating the Object Model</span></span>](creating-the-object-model.md)

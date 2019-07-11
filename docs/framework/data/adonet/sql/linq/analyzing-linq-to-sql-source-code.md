---
title: Analizar el código fuente de LINQ to SQL
ms.date: 03/30/2017
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
ms.openlocfilehash: e34364496a791031cc87cf07efd3d2adca39d93c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743594"
---
# <a name="analyzing-linq-to-sql-source-code"></a><span data-ttu-id="db8b9-102">Analizar el código fuente de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="db8b9-102">Analyzing LINQ to SQL Source Code</span></span>
<span data-ttu-id="db8b9-103">Con ayuda de los pasos siguientes, puede generar código fuente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilizando la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="db8b9-103">By using the following steps, you can produce [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] source code from the Northwind sample database.</span></span> <span data-ttu-id="db8b9-104">Puede comparar elementos del modelo de objetos con elementos de la base de datos para ver mejor cómo se asignan los distintos elementos.</span><span class="sxs-lookup"><span data-stu-id="db8b9-104">You can compare elements of the object model with elements of the database to better see how different items are mapped.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db8b9-105">Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para generar este código.</span><span class="sxs-lookup"><span data-stu-id="db8b9-105">Developers using Visual Studio can use the O/R Designer to produce this code.</span></span>  
  
1. <span data-ttu-id="db8b9-106">Si aún no tiene la base de datos de ejemplo Northwind en su equipo de desarrollo, puede descargarla de forma gratuita.</span><span class="sxs-lookup"><span data-stu-id="db8b9-106">If you do not already have the Northwind sample database on your development computer, you can download it free of charge.</span></span> <span data-ttu-id="db8b9-107">Para obtener más información, consulte [descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="db8b9-107">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
2. <span data-ttu-id="db8b9-108">Utilice la herramienta de línea de comandos SqlMetal para generar un archivo de código fuente de Visual Basic o C#.</span><span class="sxs-lookup"><span data-stu-id="db8b9-108">Use the SqlMetal command-line tool to generate a Visual Basic or C# source file.</span></span> <span data-ttu-id="db8b9-109">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="db8b9-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span> <span data-ttu-id="db8b9-110">Si escribe los comandos siguientes en un símbolo del sistema, puede generar archivos de código fuente de Visual Basic y C# que incluyan procedimientos almacenados y funciones:</span><span class="sxs-lookup"><span data-stu-id="db8b9-110">By typing the following commands at a command prompt, you can generate Visual Basic and C# source files that include stored procedures and functions:</span></span>  
  
    - `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    - `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a><span data-ttu-id="db8b9-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="db8b9-111">See also</span></span>

- [<span data-ttu-id="db8b9-112">Referencia</span><span class="sxs-lookup"><span data-stu-id="db8b9-112">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
- [<span data-ttu-id="db8b9-113">Información general</span><span class="sxs-lookup"><span data-stu-id="db8b9-113">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)

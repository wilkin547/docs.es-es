---
title: Analizar el código fuente de LINQ to SQL
ms.date: 03/30/2017
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
ms.openlocfilehash: 35bc4988b8b9845ce6f45bab6849cd4b53a858ec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592484"
---
# <a name="analyzing-linq-to-sql-source-code"></a><span data-ttu-id="16c12-102">Analizar el código fuente de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="16c12-102">Analyzing LINQ to SQL Source Code</span></span>
<span data-ttu-id="16c12-103">Con ayuda de los pasos siguientes, puede generar código fuente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilizando la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="16c12-103">By using the following steps, you can produce [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] source code from the Northwind sample database.</span></span> <span data-ttu-id="16c12-104">Puede comparar elementos del modelo de objetos con elementos de la base de datos para ver mejor cómo se asignan los distintos elementos.</span><span class="sxs-lookup"><span data-stu-id="16c12-104">You can compare elements of the object model with elements of the database to better see how different items are mapped.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16c12-105">Los desarrolladores que usan Visual Studio pueden usar el [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] para generar este código.</span><span class="sxs-lookup"><span data-stu-id="16c12-105">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to produce this code.</span></span>  
  
1. <span data-ttu-id="16c12-106">Si aún no tiene la base de datos de ejemplo Northwind en su equipo de desarrollo, puede descargarla de forma gratuita.</span><span class="sxs-lookup"><span data-stu-id="16c12-106">If you do not already have the Northwind sample database on your development computer, you can download it free of charge.</span></span> <span data-ttu-id="16c12-107">Para obtener más información, consulte [descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="16c12-107">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
2. <span data-ttu-id="16c12-108">Utilice la herramienta de línea de comandos SqlMetal para generar un archivo de código fuente de Visual Basic o C#.</span><span class="sxs-lookup"><span data-stu-id="16c12-108">Use the SqlMetal command-line tool to generate a Visual Basic or C# source file.</span></span> <span data-ttu-id="16c12-109">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="16c12-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span> <span data-ttu-id="16c12-110">Si escribe los comandos siguientes en un símbolo del sistema, puede generar archivos de código fuente de Visual Basic y C# que incluyan procedimientos almacenados y funciones:</span><span class="sxs-lookup"><span data-stu-id="16c12-110">By typing the following commands at a command prompt, you can generate Visual Basic and C# source files that include stored procedures and functions:</span></span>  
  
    - `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    - `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a><span data-ttu-id="16c12-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="16c12-111">See also</span></span>

- [<span data-ttu-id="16c12-112">Referencia</span><span class="sxs-lookup"><span data-stu-id="16c12-112">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
- [<span data-ttu-id="16c12-113">Información general</span><span class="sxs-lookup"><span data-stu-id="16c12-113">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)

---
description: Más información acerca de cómo analizar el código fuente de LINQ to SQL
title: Analizar el código fuente de LINQ to SQL
ms.date: 03/30/2017
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
ms.openlocfilehash: acf80b10c3bb817cf3fd87876da75a47e2fe271c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712797"
---
# <a name="analyzing-linq-to-sql-source-code"></a><span data-ttu-id="12894-103">Analizar el código fuente de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="12894-103">Analyzing LINQ to SQL Source Code</span></span>

<span data-ttu-id="12894-104">Con ayuda de los pasos siguientes, puede generar código fuente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilizando la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="12894-104">By using the following steps, you can produce [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] source code from the Northwind sample database.</span></span> <span data-ttu-id="12894-105">Puede comparar elementos del modelo de objetos con elementos de la base de datos para ver mejor cómo se asignan los distintos elementos.</span><span class="sxs-lookup"><span data-stu-id="12894-105">You can compare elements of the object model with elements of the database to better see how different items are mapped.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12894-106">Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para generar este código.</span><span class="sxs-lookup"><span data-stu-id="12894-106">Developers using Visual Studio can use the O/R Designer to produce this code.</span></span>  
  
1. <span data-ttu-id="12894-107">Si aún no tiene la base de datos de ejemplo Northwind en su equipo de desarrollo, puede descargarla de forma gratuita.</span><span class="sxs-lookup"><span data-stu-id="12894-107">If you do not already have the Northwind sample database on your development computer, you can download it free of charge.</span></span> <span data-ttu-id="12894-108">Para obtener más información, consulte [Descargar bases de datos de ejemplo](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="12894-108">For more information, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span>  
  
2. <span data-ttu-id="12894-109">Utilice la herramienta de línea de comandos SqlMetal para generar un archivo de código fuente de Visual Basic o C#.</span><span class="sxs-lookup"><span data-stu-id="12894-109">Use the SqlMetal command-line tool to generate a Visual Basic or C# source file.</span></span> <span data-ttu-id="12894-110">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="12894-110">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span> <span data-ttu-id="12894-111">Si escribe los comandos siguientes en un símbolo del sistema, puede generar archivos de código fuente de Visual Basic y C# que incluyan procedimientos almacenados y funciones:</span><span class="sxs-lookup"><span data-stu-id="12894-111">By typing the following commands at a command prompt, you can generate Visual Basic and C# source files that include stored procedures and functions:</span></span>  
  
    - `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    - `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a><span data-ttu-id="12894-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="12894-112">See also</span></span>

- [<span data-ttu-id="12894-113">Referencia</span><span class="sxs-lookup"><span data-stu-id="12894-113">Reference</span></span>](reference.md)
- [<span data-ttu-id="12894-114">Información general</span><span class="sxs-lookup"><span data-stu-id="12894-114">Background Information</span></span>](background-information.md)

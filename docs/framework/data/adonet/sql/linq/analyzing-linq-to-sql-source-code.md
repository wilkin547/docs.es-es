---
title: "Analizar el código fuente de LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e1677d8e30b083efe99f916b28672ddb6c3dd99
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="analyzing-linq-to-sql-source-code"></a><span data-ttu-id="8e404-102">Analizar el código fuente de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8e404-102">Analyzing LINQ to SQL Source Code</span></span>
<span data-ttu-id="8e404-103">Con ayuda de los pasos siguientes, puede generar código fuente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilizando la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="8e404-103">By using the following steps, you can produce [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] source code from the Northwind sample database.</span></span> <span data-ttu-id="8e404-104">Puede comparar elementos del modelo de objetos con elementos de la base de datos para ver mejor cómo se asignan los distintos elementos.</span><span class="sxs-lookup"><span data-stu-id="8e404-104">You can compare elements of the object model with elements of the database to better see how different items are mapped.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e404-105">Los desarrolladores que utilizan [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] pueden usar [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] para generar este código.</span><span class="sxs-lookup"><span data-stu-id="8e404-105">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to produce this code.</span></span>  
  
1.  <span data-ttu-id="8e404-106">Si aún no tiene la base de datos de ejemplo Northwind en su equipo de desarrollo, puede descargarla de forma gratuita.</span><span class="sxs-lookup"><span data-stu-id="8e404-106">If you do not already have the Northwind sample database on your development computer, you can download it free of charge.</span></span> <span data-ttu-id="8e404-107">Para obtener más información, consulte [descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="8e404-107">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
2.  <span data-ttu-id="8e404-108">Utilice la herramienta de línea de comandos SqlMetal para generar un archivo de código fuente de Visual Basic o C#.</span><span class="sxs-lookup"><span data-stu-id="8e404-108">Use the SqlMetal command-line tool to generate a Visual Basic or C# source file.</span></span> <span data-ttu-id="8e404-109">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="8e404-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span> <span data-ttu-id="8e404-110">Si escribe los comandos siguientes en un símbolo del sistema, puede generar archivos de código fuente de Visual Basic y C# que incluyan procedimientos almacenados y funciones:</span><span class="sxs-lookup"><span data-stu-id="8e404-110">By typing the following commands at a command prompt, you can generate Visual Basic and C# source files that include stored procedures and functions:</span></span>  
  
    -   `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    -   `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a><span data-ttu-id="8e404-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e404-111">See Also</span></span>  
 [<span data-ttu-id="8e404-112">Referencia</span><span class="sxs-lookup"><span data-stu-id="8e404-112">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [<span data-ttu-id="8e404-113">Información general</span><span class="sxs-lookup"><span data-stu-id="8e404-113">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)

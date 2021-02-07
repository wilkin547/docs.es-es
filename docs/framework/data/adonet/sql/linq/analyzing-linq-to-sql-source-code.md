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
# <a name="analyzing-linq-to-sql-source-code"></a>Analizar el código fuente de LINQ to SQL

Con ayuda de los pasos siguientes, puede generar código fuente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilizando la base de datos de ejemplo Northwind. Puede comparar elementos del modelo de objetos con elementos de la base de datos para ver mejor cómo se asignan los distintos elementos.  
  
> [!NOTE]
> Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para generar este código.  
  
1. Si aún no tiene la base de datos de ejemplo Northwind en su equipo de desarrollo, puede descargarla de forma gratuita. Para obtener más información, consulte [Descargar bases de datos de ejemplo](downloading-sample-databases.md).  
  
2. Utilice la herramienta de línea de comandos SqlMetal para generar un archivo de código fuente de Visual Basic o C#. Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md). Si escribe los comandos siguientes en un símbolo del sistema, puede generar archivos de código fuente de Visual Basic y C# que incluyan procedimientos almacenados y funciones:  
  
    - `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    - `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a>Vea también

- [Referencia](reference.md)
- [Información general](background-information.md)

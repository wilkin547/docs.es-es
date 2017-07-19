---
title: "Asignaciones de tipos SQL-CLR personalizadas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d916c7fb-4b56-4214-acbe-5e23365047b2
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Asignaciones de tipos SQL-CLR personalizadas
La asignación de tipos entre SQL Server y Common Language Runtime \(CLR\) se especifica automáticamente al usar la herramienta de línea de comandos SQLMetal, Object Relational Designer.  
  
 Cuando no se realiza ninguna asignación personalizada, estas herramientas asignan las asignaciones de tipos predeterminadas como se describe en [Correspondencia de tipos SQL\-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  Si desea que las asignaciones de tipos sean distintas de las predeterminadas, tendrá que hacer alguna personalización de ellas.  
  
 Al personalizar las asignaciones de tipos, el enfoque recomendado es realizar los cambios en un archivo DBML intermedio.  Después, el archivo DBML personalizado se debe usar al crear los archivos de código y de asignación con SQLMetal u Object Relational Designer.  
  
 Una vez creada una instancia del objeto <xref:System.Data.Linq.DataContext> desde los archivos de código y de asignación, el método <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName> crea una base de datos basándose en las asignaciones de tipos especificadas.  Si no hay atributos `type` de CLR especificados en las asignaciones, se usarán las asignaciones de tipos predeterminadas.  
  
## Personalización con SQLMetal o con Object Relational Designer  
 Con SQLMetal o con Object Relational Designer puede crear automáticamente un modelo de objetos que incluye información de asignación dentro o fuera del archivo de código.  Dado que SQLMetal o con Object Relational Designer sobrescribe estos archivos, cada vez que vuelve a crear las asignaciones, el método recomendado para especificar las asignaciones de tipos personalizadas es personalizar un archivo DBML.  
  
 Para personalizar las asignaciones de tipos con SQLMetal o con Object Relational Designer, primero genere un archivo DBML.  Luego, antes de generar el archivo de código o el archivo de asignación, modifique el archivo DBML para identificar las asignaciones de tipos deseadas.  Con SQLMetal, tiene que cambiar manualmente los atributos `Type` y `DbType` del archivo DBML para hacer las personalizaciones de asignación de tipos.  Con Object Relational Designer, puede hacer los cambios en el Diseñador.  Para obtener más información sobre cómo utilizar Object Relational Designer, vea [LINQ to SQL Tools en Visual Studio](../Topic/LINQ%20to%20SQL%20Tools%20in%20Visual%20Studio2.md).  
  
> [!NOTE]
>  Algunas asignaciones de tipos pueden tener como resultado excepciones de desbordamiento o de pérdida de datos mientras se convierten a la base de datos o desde ella.  Revise cuidadosamente la Matriz de comportamiento de la asignación de tipos en tiempo de ejecución en [Correspondencia de tipos SQL\-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md) antes de realizar ninguna personalización.  
  
 Para que SQLMetal o bien Object Relational Designer reconozcan las personalizaciones de asignación de tipos, tiene que asegurarse de que estas herramientas se proporcionan con la ruta de acceso del archivo DBML personalizado al generar el archivo de código o el archivo de asignación externa.  Aunque no es necesario para la personalización de la asignación de tipos, se recomienda que siempre separe la información de asignación de tipos del archivo de código y genere el archivo de asignación de tipos externa adicional.  Con esto permitirá alguna flexibilidad al no necesitar que se recompile el archivo de código.  
  
## Incorporación de cambios en la base de datos  
 Cuando la base de datos cambia, tendrá que actualizar el archivo DBML para reflejar esos cambios.  Uno modo de hacer esto es crear automáticamente un archivo DBML nuevo y, a continuación, volver a efectuar las personalizaciones de asignación de tipos.  Como alternativa, podría comparar las diferencias entre el archivo DBML nuevo y el archivo DBML personalizado y actualizar el archivo DBML personalizado para reflejar el cambio en la base de datos.  
  
## Vea también  
 [Correspondencia de tipos SQL\-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)   
 [Generación de código en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
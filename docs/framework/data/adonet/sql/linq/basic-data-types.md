---
title: "Tipos de datos b&#225;sicos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Tipos de datos b&#225;sicos
Como las consultas de LINQ to SQL se convierten a Transact\-SQL antes de ejecutarlas en Microsoft SQL Server,  LINQ to SQL admite una funcionalidad muy similar a la integrada en SQL Server para los tipos de datos básicos.  
  
## Convertir  
 Se habilitan las conversiones implícitas o explícitas de tipos CLR de origen a tipos CLR de destino si hay una conversión similar válida en SQL Server.  Para obtener más información acerca de la conversión de CLR, vea [CType \(Función\)](../Topic/CType%20Function%20\(Visual%20Basic\).md) \([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\) y [as](../Topic/as%20\(C%23%20Reference\).md).  Después de la conversión, las conversiones de tipos cambian el comportamiento de las operaciones realizadas en una expresión CLR para coincidir con el comportamiento de otras expresiones CLR que tienen una asignación natural al tipo de destino. Las conversiones de tipos también se pueden convertir en el contexto de la asignación de herencia.  Los tipos de los objetos se pueden convertir a subtipos de entidad más específicos de forma que se pueda tener acceso a los datos específicos de su subtipo.  
  
## Operadores de igualdad  
 LINQ to SQL admite los siguientes operadores de igualdad en los tipos de datos básicos dentro de las consultas de LINQ to SQL:  
  
-   Operador de igualdad y desigualdad: se admiten operadores de igualdad y desigualdad para los tipos numéricos <xref:System.Boolean>, <xref:System.DateTime> y <xref:System.TimeSpan>.  Para obtener más información sobre los operadores `=` y `<>` de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)], vea [Operadores de comparación](../Topic/Comparison%20Operators%20\(Visual%20Basic\).md). Para obtener más información sobre los operadores de comparación de C\# `==` y `!=`, vea [\=\= \(Operador\)](../Topic/==%20Operator%20\(C%23%20Reference\).md) y [\!\= \(Operador\)](../Topic/!=%20Operator%20\(C%23%20Reference\).md), respectivamente.  
  
-   Operador Is: el operador `IS` tiene un equivalente compatible cuando se utiliza la asignación de herencia.  Se puede utilizar en lugar de probar directamente la columna discriminadora para determinar si un objeto es de un tipo de entidad concreto, y se convierte en una marca de verificación en la columna discriminadora.  Para obtener más información acerca de los operadores de Visual Basic y C\#, vea [Is \(Operador\)](../Topic/Is%20Operator%20\(Visual%20Basic\).md) y [is](../Topic/is%20\(C%23%20Reference\).md).  
  
## Vea también  
 [Correspondencia de tipos SQL\-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)   
 [Funciones y tipos de datos](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
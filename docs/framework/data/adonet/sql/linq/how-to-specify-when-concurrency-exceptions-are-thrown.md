---
title: "C&#243;mo: Especificar cu&#225;ndo se producen excepciones de simultaneidad | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Especificar cu&#225;ndo se producen excepciones de simultaneidad
En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], se inicia una excepción <xref:System.Data.Linq.ChangeConflictException> cuando los objetos no se actualizan debido a conflictos de simultaneidad optimista.  Para obtener más información, consulta [Simultaneidad optimista: Información general](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
 Antes de enviar cambios a la base de datos, puede especificar cuándo se deberían iniciar excepciones de simultaneidad:  
  
-   Iniciar la excepción en el primer error \(<xref:System.Data.Linq.ConflictMode>\).  
  
-   Finalizar todos los intentos de actualización, acumular todos los errores e informar de todos ellos en la excepción \(<xref:System.Data.Linq.ConflictMode>\).  
  
 Cuando se inicia, la excepción <xref:System.Data.Linq.ChangeConflictException> proporciona acceso a una colección <xref:System.Data.Linq.ChangeConflictCollection>.  Esta colección proporciona detalles sobre cada conflicto \(asignado a un único intento de actualización con error\), incluido el acceso a la colección <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>.  Cada conflicto de miembro se asigna a un único miembro en la actualización que no pasó la comprobación de simultaneidad.  
  
## Ejemplo  
 El código siguiente muestra ejemplos de ambos valores.  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## Vea también  
 [Cómo: Administrar los conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)   
 [Crear y enviar cambios en los datos](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
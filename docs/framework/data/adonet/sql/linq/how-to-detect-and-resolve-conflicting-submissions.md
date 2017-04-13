---
title: "C&#243;mo: Detectar y resolver env&#237;os de datos en conflicto | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Detectar y resolver env&#237;os de datos en conflicto
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona muchos recursos para detectar y resolver los conflictos que ocasionan los cambios que realizan varios usuarios en la base de datos.  Para obtener más información, consulta [Cómo: Administrar los conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra un bloque `try`\/`catch` que detecta una excepción <xref:System.Data.Linq.ChangeConflictException>.  La información de entidad y miembro de cada conflicto se muestra en la ventana de la consola.  
  
> [!NOTE]
>  Debe incluir la directiva `using System.Reflection` \(`Imports System.Reflection` en Visual Basic\) para habilitar la recuperación de la información.  Para obtener más información, consulta <xref:System.Reflection>.  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## Vea también  
 [Crear y enviar cambios en los datos](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)   
 [Cómo: Administrar los conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
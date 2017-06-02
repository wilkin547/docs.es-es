---
title: "C&#243;mo: Enviar los cambios a la base de datos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c7cba174-9d40-491d-b32c-f2d73b7e9eab
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Enviar los cambios a la base de datos
Con independencia de los cambios que se efectúen en los objetos, éstos sólo se realizan en las réplicas en memoria.  Los cambios no se aplican a los datos reales de la base de datos.  Los cambios no se transmiten al servidor hasta que se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> explícitamente en <xref:System.Data.Linq.DataContext>.  
  
 Al realizar esta llamada, <xref:System.Data.Linq.DataContext> intenta convertir los cambios a comandos SQL equivalentes.  Puede utilizar su propia lógica personalizada para invalidar estas acciones, pero el orden de envío lo controla un servicio de <xref:System.Data.Linq.DataContext> que se conoce como *procesador de cambios*.  Todo ocurre en este orden:  
  
1.  Al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] examina el conjunto de objetos conocidos para determinar si se les han adjuntado nuevas instancias.  En caso afirmativo, estas nuevas instancias se agregan al conjunto de objetos con seguimiento.  
  
2.  Todos los objetos que tienen cambios pendientes se ordenan en una secuencia de objetos de acuerdo con las dependencias entre ellos.  Los objetos con cambios que dependen de otros objetos se ordenan según sus dependencias.  
  
3.  Inmediatamente antes de que se transmitan los verdaderos cambios, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] inicia una transacción para encapsular la serie de comandos individuales.  
  
4.  Los cambios en los objetos se convierten uno a uno en comandos SQL y se envían al servidor.  
  
 En este punto, cualquier error detectado por la base de datos hace que se detenga el proceso de envío, y se inicia una excepción.  Todos los cambios de la base de datos se revierten, como si no se hubiese enviado nada.  <xref:System.Data.Linq.DataContext> mantiene un registro completo de todos los cambios.  Por lo tanto, se puede intentar corregir el problema y llamar de nuevo a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, como en el ejemplo de código siguiente.  
  
## Ejemplo  
 Cuando la transacción relacionada con el envío se completa correctamente, <xref:System.Data.Linq.DataContext> recibe los cambios de los objetos sin tener en cuenta la información de seguimiento de cambios.  
  
 [!code-csharp[DLinqSubmittingChanges#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#1)]
 [!code-vb[DLinqSubmittingChanges#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#1)]  
  
## Vea también  
 [Cómo: Detectar y resolver envíos de datos en conflicto](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)   
 [Cómo: Administrar los conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)   
 [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)   
 [Crear y enviar cambios en los datos](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
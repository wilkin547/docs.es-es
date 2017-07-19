---
title: "Personalizar las operaciones mediante procedimientos almacenados exclusivamente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aedbecc1-c33c-4fb4-8861-fdf7e1dc6b8a
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Personalizar las operaciones mediante procedimientos almacenados exclusivamente
Los procedimientos almacenados representan un enfoque común para invalidar el comportamiento predeterminado.  Los ejemplos de este tema muestran cómo utilizar los contenedores de método generados para los procedimientos almacenados, y cómo se puede llamar directamente a los procedimientos almacenados.  
  
 Si utiliza [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], puede usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para asignar los procedimientos almacenados para realizar operaciones de inserción, actualización y eliminación.  
  
> [!NOTE]
>  Para volver a leer los valores generados por la base de datos, utilice parámetros de salida en los procedimientos almacenados.  Si no puede usar parámetros de salida, escriba una implementación de método parcial en lugar de confiar en las invalidaciones generadas por el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].  Los miembros asignados a los valores generados por la base de datos deben establecerse en los valores adecuados una vez que se ha completado correctamente una operación `INSERT` o `UPDATE`.  Para obtener más información, consulte [Responsabilidades del desarrollador en la invalidación del comportamiento predeterminado](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo siguiente se da por hecho que la clase `Northwind` contiene dos métodos para llamar a los procedimientos almacenados que se utilizan para las invalidaciones en una clase derivada.  
  
### Código  
 [!code-csharp[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#1)]  
  
## Ejemplo  
  
### Descripción  
 La clase siguiente utiliza estos métodos para la invalidación.  
  
### Código  
 [!code-csharp[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#2)]  
  
## Ejemplo  
  
### Descripción  
 Puede utilizar `NorthwindThroughSprocs` de la misma forma que utilizaría `Northwnd`.  
  
### Código  
 [!code-csharp[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#3)]  
  
## Vea también  
 [Responsabilidades del desarrollador en la invalidación del comportamiento predeterminado](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
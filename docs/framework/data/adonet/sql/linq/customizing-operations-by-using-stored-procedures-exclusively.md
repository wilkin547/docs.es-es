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
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Personalizar las operaciones mediante procedimientos almacenados exclusivamente
Un escenario común es obtener acceso a los datos utilizando únicamente procedimientos almacenados.  
  
## Ejemplo  
  
### Descripción  
 Puede modificar el ejemplo proporcionado en [Personalizar las operaciones mediante procedimientos almacenados exclusivamente](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) reemplazando incluso la primera consulta \(que provoca la ejecución de SQL dinámico\) con una llamada a método que incluya un procedimiento almacenado.  
  
 Supongamos que `CustomersByCity` es el método, como en el siguiente ejemplo.  
  
### Código  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 El código siguiente se ejecuta sin SQL dinámico.  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## Vea también  
 [Responsabilidades del desarrollador en la invalidación del comportamiento predeterminado](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
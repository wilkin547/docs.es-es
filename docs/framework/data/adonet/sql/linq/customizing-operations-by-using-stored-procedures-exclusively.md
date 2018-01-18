---
title: Personalizar operaciones utilizando exclusivamente procedimientos almacenados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b379f6eec503f5dffc5a01dd8f5cbc79e19b8c40
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a>Personalizar operaciones utilizando exclusivamente procedimientos almacenados
Un escenario común es obtener acceso a los datos utilizando únicamente procedimientos almacenados.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 Puede modificar el ejemplo proporcionado en [personalizar operaciones utilizando procedimientos almacenados](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) reemplazando incluso la primera consulta (que hace que la ejecución de SQL dinámica) con una llamada al método que contiene un procedimiento almacenado.  
  
 Supongamos que `CustomersByCity` es el método, como en el siguiente ejemplo.  
  
### <a name="code"></a>Código  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 El código siguiente se ejecuta sin SQL dinámico.  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Vea también  
 [Responsabilidades del desarrollador al invalidar un comportamiento predeterminado](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)

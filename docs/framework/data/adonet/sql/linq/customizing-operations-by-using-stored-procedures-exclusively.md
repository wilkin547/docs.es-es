---
description: Obtener más información acerca de cómo personalizar las operaciones mediante procedimientos almacenados exclusivamente
title: Personalizar operaciones utilizando exclusivamente procedimientos almacenados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 4ddcc6b4face1abccb502e12617105a734bb5f0b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729554"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a>Personalizar operaciones utilizando exclusivamente procedimientos almacenados

Un escenario común es obtener acceso a los datos utilizando únicamente procedimientos almacenados.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  

 Puede modificar el ejemplo que se proporciona en la [Personalización de operaciones utilizando procedimientos almacenados](customizing-operations-by-using-stored-procedures.md) reemplazando incluso la primera consulta (que provoca la ejecución dinámica de SQL) con una llamada al método que contiene un procedimiento almacenado.  
  
 Supongamos que `CustomersByCity` es el método, como en el siguiente ejemplo.  
  
### <a name="code"></a>Código  

 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 El código siguiente se ejecuta sin SQL dinámico.  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Vea también

- [Responsabilidades del desarrollador al invalidar un comportamiento predeterminado](responsibilities-of-the-developer-in-overriding-default-behavior.md)

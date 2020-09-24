---
title: Personalizar operaciones utilizando exclusivamente procedimientos almacenados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 78db5cf448a19056d7265ab84d97d055748c3faa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164329"
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
  
## <a name="see-also"></a>Consulte también

- [Responsabilidades del desarrollador al invalidar un comportamiento predeterminado](responsibilities-of-the-developer-in-overriding-default-behavior.md)

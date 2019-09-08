---
title: Llamadas a métodos locales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
ms.openlocfilehash: ec288d5ac2f6466860362be82c619c89204e8f31
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781422"
---
# <a name="local-method-calls"></a>Llamadas a métodos locales
Las llamadas a métodos locales son las que se ejecutan dentro del modelo de objetos. Las llamadas a métodos remotos son la que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte a SQL y después transmite al motor de base de datos para su ejecución. Las llamadas a métodos locales son [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] necesarias cuando no puede convertir la llamada en SQL. De lo contrario, se produce una excepción <xref:System.InvalidOperationException>.  
  
## <a name="example-1"></a>Ejemplo 1  
 En el ejemplo siguiente, se asigna una clase `Order` a la tabla Orders de la base de datos de ejemplo Northwind. Se ha agregado a la clase un método de instancia local.  
  
 En la consulta 1, el constructor de la clase `Order` se ejecuta localmente. En la consulta 2, si [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] intentara convertir `LocalInstanceMethod()` a SQL, se produciría un error y se iniciaría una excepción <xref:System.InvalidOperationException>. Pero, dado que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona compatibilidad con las llamadas a métodos locales, la consulta 2 no iniciará una excepción.  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Información general](background-information.md)

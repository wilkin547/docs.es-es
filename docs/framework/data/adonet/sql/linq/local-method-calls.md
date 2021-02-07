---
description: 'Más información sobre: llamadas a métodos locales'
title: Llamadas a métodos locales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
ms.openlocfilehash: 7f3870a700ac86e87e3464f0bc6aaccbb2525168
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695546"
---
# <a name="local-method-calls"></a>Llamadas a métodos locales

Las llamadas a métodos locales son las que se ejecutan dentro del modelo de objetos. Las llamadas a métodos remotos son la que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte a SQL y después transmite al motor de base de datos para su ejecución. Las llamadas a métodos locales son necesarias cuando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no puede convertir la llamada en SQL. De lo contrario, se produce una excepción <xref:System.InvalidOperationException>.  
  
## <a name="example-1"></a>Ejemplo 1  

 En el ejemplo siguiente, se asigna una clase `Order` a la tabla Orders de la base de datos de ejemplo Northwind. Se ha agregado a la clase un método de instancia local.  
  
 En la consulta 1, el constructor de la clase `Order` se ejecuta localmente. En la consulta 2, si [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] intentara convertir `LocalInstanceMethod()` a SQL, se produciría un error y se iniciaría una excepción <xref:System.InvalidOperationException>. Pero, dado que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona compatibilidad con las llamadas a métodos locales, la consulta 2 no iniciará una excepción.  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Información general](background-information.md)

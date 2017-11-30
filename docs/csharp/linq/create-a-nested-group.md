---
title: Crear un grupo anidado
description: "Cómo crear un grupo anidado."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: 232aa46d975d7c338bbc776e3867f2e566601fde
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="create-a-nested-group"></a>Crear un grupo anidado

En el ejemplo siguiente se muestra cómo crear grupos anidados en una expresión de consulta LINQ. Cada grupo creado a partir del nivel académico o del año de los estudiantes se subdivide en grupos según sus nombres.  
  
## <a name="example"></a>Ejemplo

 > [!NOTE]
 > Este ejemplo contiene referencias a objetos que se definen en el código de ejemplo de [Query a collection of objects](query-a-collection-of-objects.md) (Consultar una colección de objetos). 

 [!code-csharp[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]  
  
 Tenga en cuenta que se necesitan tres bucles `foreach` anidados para recorrer en iteración los elementos internos de un grupo anidado.  
  
## <a name="see-also"></a>Vea también  
 [Expresiones de consulta LINQ](index.md)

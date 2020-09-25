---
title: Identidad de objetos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c788f2f9-65cc-4455-9907-e8388a268e00
ms.openlocfilehash: 1a1617b4fb15a6adf94c0241c3ba577308c51a8b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169432"
---
# <a name="object-identity"></a>Identidad de objetos

Los objetos en tiempo de ejecución tienen identidades únicas. Dos variables que hacen referencia al mismo objeto en realidad hacen referencia a la misma instancia del objeto. Por este motivo, los cambios que se realizan a través de una variable están visibles inmediatamente a través de la otra.  
  
 Las filas de una tabla de base de datos relacional no tienen identidades únicas. Dado que cada fila tiene una clave principal única, dos filas no comparten el mismo valor de clave. Sin embargo, este hecho restringe sólo el contenido de la tabla de base de datos.  
  
 En realidad, la mayoría de las veces los datos se extraen de la base de datos y se colocan en un nivel diferente, donde una aplicación trabaja con ellos. Éste es el modelo que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite. Cuando los datos se extraen de la base de datos como filas, no se espera que dos filas que representan los mismos datos realmente se correspondan con las mismas instancias de fila. Si consulta un cliente concreto dos veces, obtiene dos filas de datos. Cada fila contiene la misma información.  
  
 En el caso de los objetos, se espera algo muy diferente. Se espera que, si se solicita la misma información a <xref:System.Data.Linq.DataContext> varias veces, de hecho se obtendrá la misma instancia de objeto. Este comportamiento es el esperado porque los objetos tienen un significado especial para una aplicación y se espera que se comporten como objetos. Se han diseñado como jerarquías o gráficos. Lo que se espera es que se recuperarán como tales y no que se recibirán múltiples instancias replicadas sólo porque se solicitó lo mismo más de una vez.  
  
 En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], <xref:System.Data.Linq.DataContext> administra la identidad de objeto. Siempre que se recupera una nueva fila de la base de datos, la fila se registra en una tabla de identidad según su clave principal y se crea un nuevo objeto. Siempre que se recupera esa misma fila, la instancia de objeto original se devuelve a la aplicación. De esta manera, <xref:System.Data.Linq.DataContext> convierte el concepto de identidad desde el punto de vista de la base de datos (es decir, claves principales) en el concepto de identidad desde el punto de vista del lenguaje (es decir, instancias). La aplicación solo ve el objeto en el estado en que se recuperó por primera vez. Los nuevos datos, si son diferentes, se descartan. Para obtener más información, vea [recuperar objetos de la memoria caché de identidades](retrieving-objects-from-the-identity-cache.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utiliza este enfoque para administrar la integridad de los objetos locales con el fin de admitir las actualizaciones optimistas. Dado que los únicos cambios que se producen después de crear el objeto son los realizados por la aplicación, la intención de la aplicación está clara. Si en ese período de tiempo un tercero ha realizado cambios, se identifican en el momento en que se llama a `SubmitChanges()`.  
  
> [!NOTE]
> Si el objeto solicitado por la consulta se puede identificar con facilidad como ya recuperado, no se ejecuta ninguna consulta. La tabla de identidad actúa como caché de todos los objetos previamente recuperados.  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="object-caching-example-1"></a>Primer ejemplo de almacenamiento de objetos en caché  

 En este ejemplo, si ejecuta la misma consulta dos veces, en cada ocasión recibe una referencia al mismo objeto en memoria.  
  
 [!code-csharp[DLinqObjectIdentity#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectIdentity/cs/Program.cs#1)]
 [!code-vb[DLinqObjectIdentity#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectIdentity/vb/Module1.vb#1)]  
  
### <a name="object-caching-example-2"></a>Segundo ejemplo de almacenamiento de objetos en caché  

 En este ejemplo, si ejecuta consultas diferentes que devuelven la misma fila de la base de datos, en cada ocasión recibe una referencia al mismo objeto en memoria.  
  
 [!code-csharp[DLinqObjectIdentity#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectIdentity/cs/Program.cs#2)]
 [!code-vb[DLinqObjectIdentity#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectIdentity/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Consulte también

- [Información general](background-information.md)

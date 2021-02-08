---
description: 'Más información acerca de cómo: controlar la cantidad de datos relacionados que se recuperan'
title: Procedimiento para controlar la cantidad de datos relacionados que se recupera
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: efdc203e-3da9-4477-815e-54f10c3d7c6c
ms.openlocfilehash: becf1282d18d5c630da3e3be27c62ebae404d940
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786048"
---
# <a name="how-to-control-how-much-related-data-is-retrieved"></a>Procedimiento para controlar la cantidad de datos relacionados que se recupera

Utilice el método <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> para especificar qué datos relacionados con el destino principal deben recuperarse al mismo tiempo. Por ejemplo, si sabe que va a necesitar información sobre los pedidos de los clientes, puede utilizar <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> para asegurarse de que la información de los pedidos se va a recuperar al mismo tiempo que la información de los clientes. Con este enfoque, sólo se requiere un viaje a la base de datos para ambos conjuntos de información.  
  
> [!NOTE]
> Puede recuperar datos relacionados con el destino principal de la consulta recuperando un producto cruzado como una gran proyección; por ejemplo, puede recuperar los pedidos cuando el destino de la consulta son los clientes. Sin embargo, este enfoque a menudo tiene desventajas. Por ejemplo, los resultados son simples proyecciones, no entidades que se puedan cambiar y conservar mediante [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Además, podría recuperar una gran cantidad de datos que no necesita.  
  
## <a name="example"></a>Ejemplo  

 En el siguiente ejemplo, se recuperan todos los `Orders` de todos los `Customers` de Londres cuando se ejecuta la consulta. En consecuencia, el acceso posterior a la propiedad `Orders` de un objeto `Customer` no desencadena una nueva consulta de base de datos.  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Consultar la base de datos](querying-the-database.md)

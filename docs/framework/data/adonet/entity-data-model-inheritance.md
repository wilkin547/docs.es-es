---
title: 'Entity Data Model: Herencia'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6e6207087524a1ec1201511a91a810f02449e610
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="entity-data-model-inheritance"></a>Entity Data Model: Herencia
Entity Data Model (EDM) admite la herencia de [tipos de entidad](../../../../docs/framework/data/adonet/entity-type.md). La herencia en EDM es similar a la herencia para las clases en los lenguajes de programación orientados a objetos. Al igual que con las clases en lenguajes orientados a objetos, en un modelo conceptual se puede definir un tipo de entidad (un *tipo derivado*) que se hereda de otro tipo de entidad (la *tipo base*). Sin embargo, a diferencia de las clases en la programación orientada a objetos, en un modelo conceptual el tipo derivado siempre hereda todas las [propiedades](../../../../docs/framework/data/adonet/property.md) y [propiedades de navegación](../../../../docs/framework/data/adonet/navigation-property.md) del tipo base. No se pueden reemplazar las propiedades heredadas en un tipo derivado.  
  
 En un modelo conceptual, se pueden crear jerarquías de herencia en las que un tipo derivado hereda de otro tipo derivado. El tipo en la parte superior de la jerarquía (un tipo de la jerarquía que no es un tipo derivado) se denomina la *tipo de raíz*. En una jerarquía de herencia, la [clave de entidad](../../../../docs/framework/data/adonet/entity-key.md) debe definirse en el tipo raíz.  
  
 No se pueden crear jerarquías de herencia en las que un tipo derivado hereda de más de un tipo. Por ejemplo, en un modelo conceptual con un tipo de entidad `Book`, se podrían definir tipos derivados `FictionBook` y `NonFictionBook` que hereden de `Book`. Sin embargo, no se podría definir un tipo que herede de los tipos `FictionBook` y `NonFictionBook`.  
  
## <a name="example"></a>Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con cuatro tipos de entidad: `Book`, `FictionBook`, `Publisher` y `Author`. El tipo de entidad `FictionBook` es un tipo derivado, que hereda del tipo de entidad `Book`. El tipo `FictionBook` hereda las propiedades `ISBN (Key)`, `Title` y `Revision`, y define una propiedad adicional denominada `Genre`.  
  
 ![Herencia](../../../../docs/framework/data/adonet/media/inheritanceexample.gif "InheritanceExample")  
  
 El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales. El código CSDL siguiente define un tipo de entidad, `FictionBook`, que hereda del tipo `Book` (como en el diagrama anterior):  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## <a name="see-also"></a>Vea también  
 [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)

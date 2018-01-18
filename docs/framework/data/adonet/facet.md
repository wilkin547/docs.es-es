---
title: facet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91c4e6aa-3e54-4b6c-a38a-abf27808cc85
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 23346fe2095cea2b3f0d705c7d6d8914c35c06f7
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="facet"></a>facet
A *faceta* se usa para agregar detalles a una definición de propiedad de tipo primitivo. A [propiedad](../../../../docs/framework/data/adonet/property.md) definición contiene información sobre el tipo de propiedad, pero a menudo es necesario más detalle. Por ejemplo, un tipo de entidad en un modelo conceptual podría tener una propiedad de tipo `String` cuyo valor no se puede establecer en NULL. Las facetas permiten especificar este nivel de detalle.  
  
 En la siguiente tabla se describen las facetas que se admiten en EDM.  
  
> [!NOTE]
>  El entorno de tiempo de ejecución que utiliza una implementación de EDM determina los valores exactos y los comportamientos de las facetas.  
  
|Faceta|Descripción|Se aplica a|  
|-----------|-----------------|----------------|  
|`Collation`|Especifica la secuencia de intercalación (o secuencia de orden) que se va a usar cuando se realicen las operaciones de comparación y ordenación sobre los valores de la propiedad.|`String`|  
|`ConcurrencyMode`|Indica que el valor de propiedad se debería utilizar para las comprobaciones de la simultaneidad optimista.|Todas las propiedades de tipo primitivo|  
|`Default`|Especifica el valor predeterminado de la propiedad si no se proporciona ningún valor al crear las instancias.|Todas las propiedades de tipo primitivo|  
|`FixedLength`|Especifica si la longitud del valor de propiedad puede variar.|`Binary`, `String`|  
|`MaxLength`|Especifica la longitud máxima del valor de propiedad.|`Binary`, `String`|  
|`Nullable`|Especifica si la propiedad puede tener un valor NULL.|Todas las propiedades de tipo primitivo|  
|`Precision`|Para las propiedades de tipo `Decimal`, especifica el número de dígitos que puede tener un valor de propiedad. Para las propiedades de tipo `Time`, `DateTime` y `DateTimeOffset`, especifica el número de dígitos para la parte fraccionaria de los segundos del valor de propiedad.|`DateTime`, `DateTimeOffset`, `Decimal`, `Time`,|  
|`Scale`|Especifica el número de dígitos que puede haber a la derecha del separador decimal para el valor de propiedad.|Decimal|  
|`Unicode`|Indica si el valor de propiedad está almacenado como Unicode.|`String`|  
  
## <a name="example"></a>Ejemplo  
 El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales. En el ejemplo siguiente CSDL, se define un tipo de entidad `Book`. Observe que las facetas se implementan como atributos XML. Los valores de faceta indican que ninguna propiedad puede estar establecida en NULL, y que los valores `Scale` y `Precision` de la propiedad `Revision` están establecidos ambos en 29.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>Vea también  
 [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)

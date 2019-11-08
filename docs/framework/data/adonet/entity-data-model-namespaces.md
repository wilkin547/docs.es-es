---
title: 'Entity Data Model: Espacios de nombres'
ms.date: 03/30/2017
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
ms.openlocfilehash: a403bcd459005ed9cea4a455fcde40c31c8caac9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738444"
---
# <a name="entity-data-model-namespaces"></a>Entity Data Model: Espacios de nombres
Un espacio de nombres en el Entity Data Model (EDM) es un contenedor abstracto para [tipos de entidad](entity-type.md), [tipos complejos](complex-type.md)y [asociaciones](association-type.md). Los espacios de nombres en EDM son similares a los de un lenguaje de programación: proporcionan el contexto para los objetos que contienen, así como una manera de eliminar la ambigüedad de objetos que tienen el mismo nombre (pero que contienen espacios de nombres diferentes).  
  
## <a name="example"></a>Ejemplo  
 El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales. En el siguiente código CSDL se utiliza un espacio de nombres para identificar un tipo que se define en un modelo conceptual diferente. En el ejemplo se define un tipo de entidad (`Publisher`) con una propiedad de tipo complejo (`Address`) que se importa del espacio de nombres `ExtendedBooksModel`. Observe que el elemento `Using` indica que se ha importado un espacio de nombres. Observe también que el tipo de la propiedad `Address` se define utilizando su nombre completo (`ExtendedBooksModel.Address`), lo que indica que este tipo se define en el espacio de nombres `ExtendedBooksModel`.  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a>Vea también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)

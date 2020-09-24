---
title: función declarada por el modelo
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: fb30dd86c29d6a7fff6f2c71d5fd892326e1fda4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147858"
---
# <a name="model-declared-function"></a>función declarada por el modelo

Una *función declarada por el modelo* es una función que se declara en un modelo conceptual, pero que no está definida en ese modelo conceptual. La función se podría definir en el entorno de almacenamiento u hospedaje. Por ejemplo, una función declarada por modelo se podría asignar a una función definida en una base de datos, exponiendo así la funcionalidad de servidor en el modelo conceptual.  
  
 La declaración de una función declarada por modelo contiene la siguiente información:  
  
- Nombre de la función. (Requerido)  
  
- El tipo del valor devuelto. (Opcional)  
  
    > [!NOTE]
    > Si no se especifica ningún valor devuelto, el tipo de valor devuelto es void.  
  
- Información de parámetro, incluidos el tipo y el nombre de parámetro. (Opcional)  
  
## <a name="example"></a>Ejemplo  

 El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales. En CSDL, una implementación de una función declarada por modelo es una importación de función (mediante el [elemento FunctionImport](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)). El siguiente CSDL define un contenedor de la entidad con una definición de importación de función. Tenga en cuenta que el tipo de valor devuelto es void porque no se especifica ningún tipo de valor devuelto.  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a>Vea también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)

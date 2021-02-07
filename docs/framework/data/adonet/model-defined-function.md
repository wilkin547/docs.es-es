---
description: 'Más información sobre: función definida por el modelo'
title: función definida por el modelo
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 146ef4a8ad8c38897b8e56b6bc1485e1e40754cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723743"
---
# <a name="model-defined-function"></a>función definida por el modelo

Una *función definida por el modelo* es una función que se define en un modelo conceptual. El cuerpo de una función definida por el modelo se expresa en [Entity SQL](./ef/language-reference/entity-sql-language.md), lo que permite expresar la función independientemente de las reglas o los lenguajes admitidos en el origen de datos.  
  
 La definición para una función definida por el modelo contiene la información siguiente:  
  
- Un nombre de función. (Requerido)  
  
- El tipo del valor devuelto. (Opcional)  
  
    > [!NOTE]
    > Si no se especifica ningún tipo de valor devuelto, este es void.  
  
- Información de parámetros. (Opcional)  
  
- Expresión [Entity SQL](./ef/language-reference/entity-sql-language.md) que define el cuerpo de la función.  
  
 Tenga en cuenta que las funciones definidas por el modelo no admiten parámetros de salida. Esta restricción se aplica para que las funciones definidas por el modelo puedan ser compuestas.  
  
## <a name="example"></a>Ejemplo  

 El diagrama siguiente muestra un modelo conceptual con tres tipos de entidades: `Book`, `Publisher` y `Author`.  
  
 ![Captura de pantalla que muestra un modelo con fecha de publicación.](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 El [Entity Framework ADO.net](./ef/index.md) usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) para definir los modelos conceptuales. El código CSDL siguiente define una función en el modelo conceptual que devuelve el número de años transcurridos desde la publicación de una instancia de `Book` (en el diagrama anterior).  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a>Vea también

- [Conceptos clave de Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
- [Entity Data Model: tipos de datos primitivos](entity-data-model-primitive-data-types.md)

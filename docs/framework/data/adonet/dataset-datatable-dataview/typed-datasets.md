---
description: 'Más información sobre: conjuntos de valores de tipos'
title: Objetos DataSet con tipo
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 698efbe52e960afe00ca337445df919545d8437e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651501"
---
# <a name="typed-datasets"></a>Objetos DataSet con tipo

Además del acceso en tiempo de ejecución a valores mediante variables débilmente tipadas, el <xref:System.Data.DataSet> proporciona acceso a los datos mediante una metáfora fuertemente tipada. Se puede tener acceso a las tablas y columnas que forman parte del **conjunto** de elementos mediante nombres descriptivos y variables fuertemente tipadas.  
  
 Un **DataSet** con tipo es una clase que se deriva de un **DataSet**. Como tal, hereda todos los métodos, eventos y propiedades de un **DataSet**. Además, un conjunto de un **DataSet** con tipo proporciona métodos, eventos y propiedades fuertemente tipados. Esto significa que se puede tener acceso a tablas y columnas por su nombre, en lugar de utilizar métodos de una colección. Aparte de la mejora de la legibilidad del código, un **conjunto** de elementos de tipo también permite que el editor de código de Visual Studio .net complete automáticamente las líneas a medida que escribe.  
  
 Además, el **conjunto de DataSet** fuertemente tipado proporciona acceso a los valores como el tipo correcto en tiempo de compilación. Con un **conjunto** de tipos fuertemente tipado, los errores de coincidencia de tipos se detectan cuando se compila el código en lugar de en tiempo de ejecución.  
  
## <a name="in-this-section"></a>En esta sección  

 [Generar conjuntos de datos fuertemente tipados](generating-strongly-typed-datasets.md)  
 Describe cómo crear y usar un **conjunto de DataSet** fuertemente tipado.  
  
 [Comentar conjuntos de datos con tipo](annotating-typed-datasets.md)  
 Describe cómo anotar el esquema del lenguaje de definición de esquemas XML (XSD) utilizado para generar un **DataSet** fuertemente tipado, a fin de proporcionar nombres descriptivos a los elementos del **conjunto** de elementos sin modificar el esquema subyacente.  
  
## <a name="see-also"></a>Vea también

- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)

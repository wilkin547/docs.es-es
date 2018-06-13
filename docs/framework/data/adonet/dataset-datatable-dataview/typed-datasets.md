---
title: Objetos DataSet con tipo
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 67c1d3a190c5a4f046d7c7da5ebbf98395a96341
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762460"
---
# <a name="typed-datasets"></a>Objetos DataSet con tipo
Además del acceso en tiempo de ejecución a valores mediante variables débilmente tipadas, el <xref:System.Data.DataSet> proporciona acceso a los datos mediante una metáfora fuertemente tipada. Tablas y columnas que forman parte de la **conjunto de datos** puede tener acceso mediante nombres descriptivos y variables fuertemente tipadas.  
  
 Un tipo **conjunto de datos** es una clase que deriva de un **conjunto de datos**. Como tal, hereda todos los métodos, eventos y propiedades de un **conjunto de datos**. Además, un tipo **conjunto de datos** proporciona métodos fuertemente tipados, eventos y propiedades. Esto significa que se puede tener acceso a tablas y columnas por su nombre, en lugar de utilizar métodos de una colección. Además de la mayor legibilidad del código, un tipo **conjunto de datos** también permite que el código de Visual Studio .NET complete automáticamente las líneas mientras escribe el editor.  
  
 Además, el fuertemente tipado **conjunto de datos** proporciona acceso a los valores del tipo correcto en tiempo de compilación. Con un fuertemente tipado **conjunto de datos**, errores de falta de coincidencia de tipos se interceptan cuando el código se compila en lugar de en tiempo de ejecución.  
  
## <a name="in-this-section"></a>En esta sección  
 [Generación de conjuntos de datos fuertemente tipados](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 Describe cómo crear y usar un fuertemente tipado **conjunto de datos**.  
  
 [Anotación de conjuntos de datos con tipo](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 Describe cómo se anota el esquema de lenguaje (XSD) de definición de esquema XML utilizado para generar un fuertemente tipado **conjunto de datos**fin de asignar **conjunto de datos** nombres descriptivos de elementos sin modificar el esquema subyacente.  
  
## <a name="see-also"></a>Vea también  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)

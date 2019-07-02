---
title: Depurar consultas de LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
ms.openlocfilehash: 38eda9f352c4a8d8590e5e57b48c694eadd0397b
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67503989"
---
# <a name="debugging-linq-to-dataset-queries"></a>Depurar consultas de LINQ to DataSet

Visual Studio admite la depuración de LINQ a código de conjunto de datos. Sin embargo, hay algunas diferencias entre depurar LINQ al código de conjunto de datos y LINQ a código administrado del conjunto de datos. Características de depuración más trabajan con LINQ para las instrucciones del conjunto de datos, incluida la ejecución paso a paso, establecer puntos de interrupción y ver los resultados que se muestran en las ventanas del depurador. Sin embargo, la ejecución aplazada de consultas tiene algunos efectos que debería tener en cuenta durante la depuración LINQ al código del conjunto de datos y hay algunas limitaciones para utilizar editar y continuar. En este tema se trata aspectos de depuración que son exclusivos de LINQ to DataSet en comparación con sin LINQ a código administrado del conjunto de datos.  
  
## <a name="viewing-results"></a>Ver los resultados  
 Puede ver el resultado de una instrucción de conjunto de datos de LINQ mediante información sobre datos, la ventana Inspección y el cuadro de diálogo Inspección rápida. Al usar una ventana de código fuente, puede pausar el puntero en una consulta en la ventana de código fuente para que aparezca una información sobre datos. Puede copiar un LINQ a conjunto de datos variable y pegarla en la ventana Inspección o en el cuadro de diálogo Inspección rápida. En LINQ to DataSet, una consulta no se evalúa cuando se crea o declara, pero solo cuando se ejecuta la consulta. Esto se denomina *ejecución aplazada*. Por consiguiente, la variable de consulta no tiene un valor hasta que se evalúe. Para obtener más información, consulte [consultas en LINQ to DataSet](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md).  
  
 Para mostrar el resultado de una consulta, el depurador debe evaluarla. Esta evaluación implícita se produce al ver un resultado de la consulta de conjunto de datos de LINQ en el depurador y tiene algunos efectos que debería considerar. Cada evaluación de la consulta lleva tiempo. Expandir el nodo de resultados lleva tiempo. Para algunas consultas, la evaluación repetida podría producir una reducción notable del rendimiento. Evaluar una consulta también puede producir efectos secundarios, que son cambios en el valor de los datos o en el estado del programa. No todas las consultas tienen los efectos secundarios. Para determinar si una consulta se puede evaluar sin ningún riesgo ni efectos secundarios, debe entender el código que implementa la consulta. Para obtener más información, consulte [efectos y expresiones](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/a7a250bs(v=vs.120)).  
  
## <a name="edit-and-continue"></a>Editar y continuar  
 Editar y continuar no admite cambios en LINQ a consultas de conjunto de datos. Si agregar, quitar o cambiar un LINQ a la instrucción de conjunto de datos durante una sesión de depuración, aparece un cuadro de diálogo indicando que editar y continuar no admite el cambio. En ese momento, puede deshacer los cambios o detener la sesión de depuración y reiniciar una nueva sesión con el código revisado.  
  
 Además, editar y continuar no permite cambiar el tipo o el valor de una variable que se usa en una instrucción de conjunto de datos de LINQ. De nuevo, puede deshacer los cambios o detener y reiniciar la sesión de depuración.  
  
 En Visual C# en Visual Studio, no se puede usar Editar y continuar en cualquier código en un método que contiene una consulta LINQ to DataSet.  
  
 En Visual Basic en Visual Studio, puede usar Editar y continuar en sin LINQ al código del conjunto de datos, incluso en un método que contiene una consulta LINQ to DataSet. Puede agregar o quitar el código antes de LINQ to DataSet instrucción, incluso si los cambios afectan al número de línea de la consulta LINQ to DataSet. Experiencia de LINQ a código de conjunto de datos de depuración de Visual Basic sigue siendo el mismo que estaba antes de incluir LINQ a conjunto de datos. No se puede cambiar, agregar o quitar una consulta LINQ to DataSet, sin embargo, a menos que detenga la depuración para aplicar los cambios.  
  
## <a name="see-also"></a>Vea también

- [Depurar código administrado](/visualstudio/debugger/debugging-managed-code)
- [Guía de programación](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)

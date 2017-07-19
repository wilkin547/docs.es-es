---
title: "Depurar consultas LINQ to DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Depurar consultas LINQ to DataSet
[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] permite depurar el código [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  Sin embargo, existen algunas diferencias entre depurar código [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] y depurar código administrado que no es [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. La mayor parte de las características de depuración funcionan con instrucciones [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], entre ellas la función de examen, de establecimiento de puntos de interrupción y el examen de resultados que se muestran en la ventana del depurador.  Sin embargo, la ejecución de consultas en diferido conlleva algunos efectos secundarios que se deben tener en cuenta al depurar código [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] y hay algunas limitaciones para utilizar Editar y continuar.  En este tema se tratan aspectos de depuración únicos para [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] en comparación con código administrado que no es [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]  
  
## Ver los resultados  
 Puede ver el resultado de una instrucción [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] mediante Información sobre datos, ventana Inspección y cuadro de diálogo Inspección rápida.  Al usar una ventana de código fuente, puede pausar el puntero en una consulta en la ventana de código fuente para que aparezca una información sobre datos.  Puede copiar una variable [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] y pegarla en la ventana Inspección o en el cuadro de diálogo Inspección rápida. En [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], una consulta no se evalúa cuando se crea o declara, sino únicamente cuando se ejecuta.  Esto se denomina *ejecución aplazada*.  Por consiguiente, la variable de consulta no tiene un valor hasta que se evalúe.  Para obtener más información, consulta [Consultas en LINQ to DataSet](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md).  
  
 Para mostrar el resultado de una consulta, el depurador debe evaluarla.  Esta evaluación implícita se produce cuando aparece un resultado de la consulta [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] en el depurador y tiene algunos efectos que debería considerar.  Cada evaluación de la consulta lleva tiempo.  Expandir el nodo de resultados lleva tiempo.  Para algunas consultas, la evaluación repetida podría producir una reducción notable del rendimiento.  Evaluar una consulta también puede producir efectos secundarios, que son cambios en el valor de los datos o en el estado del programa.  No todas las consultas tienen los efectos secundarios.  Para determinar si una consulta se puede evaluar sin ningún riesgo ni efectos secundarios, debe entender el código que implementa la consulta.  Para obtener más información, consulta [Expresiones y efectos secundarios](../Topic/Side%20Effects%20and%20Expressions.md).  
  
## Editar y continuar  
 Editar y continuar no admite los cambios a las consultas [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  Si agrega, quita o cambia una instrucción [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] durante una sesión de depuración, aparece un cuadro de diálogo indicando que Editar y continuar no admite el cambio.  En ese momento, puede deshacer los cambios o detener la sesión de depuración y reiniciar una nueva sesión con el código revisado.  
  
 Además, Editar y continuar no permite cambiar el tipo o el valor de una variable que se usa en una instrucción [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  De nuevo, puede deshacer los cambios o detener y reiniciar la sesión de depuración.  
  
 En Visual C\# en Visual Studio, no puede usar Editar y continuar en cualquier código en un método que contiene una consulta [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  
  
 En Visual Basic en Visual Studio, puede usar Editar y continuar en código sin [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], incluso en un método que contiene una consulta [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  Puede agregar o quitar el código antes de la instrucción [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], incluso si los cambios afectan al número de línea de la consulta [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]LINQ.  La experiencia en depuración de Visual Basic para código sin [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] es igual que antes de incluir [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  No se puede cambiar, agregar o quitar una consulta [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], a menos que desee detener la depuración para aplicar los cambios.  
  
## Vea también  
 [Depurar código administrado](../Topic/Debugging%20Managed%20Code.md)   
 [Guía de programación](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
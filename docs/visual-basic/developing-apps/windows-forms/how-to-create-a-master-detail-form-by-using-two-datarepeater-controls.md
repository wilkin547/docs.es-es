---
title: "C&#243;mo: Crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, tablas principal-detalle"
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# C&#243;mo: Crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Puede mostrar datos relacionados mediante dos o más controles <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> para crear un formulario principal\-detalle.  Por ejemplo, puede que desee mostrar una lista de clientes en un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> y, cuando el usuario seleccione un cliente, mostrar la lista de pedidos de ese cliente en un segundo control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
 Puede mostrar datos relacionados arrastrando elementos de detalle que comparten el mismo nodo de tabla principal desde la ventana **Orígenes de datos** hasta un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Por ejemplo, si tiene un origen de datos con una tabla Clientes y una tabla Pedidos relacionada, verá ambas tablas como nodos de nivel superior en la vista de árbol de la ventana **Orígenes de datos**.  Expanda el nodo Clientes para poder ver las columnas.  Observe que la última columna de la lista es un nodo expansible que representa la tabla Pedidos.  Este nodo representa los pedidos relacionados para un cliente.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Para mostrar datos relacionados en dos controles DataRepeater  
  
1.  Arrastre dos controles <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> desde la ficha **Visual Basic PowerPacks** del **Cuadro de herramientas** hasta un formulario o control contenedor.  
  
2.  Arrastre los controladores de tamaño y posición para ajustar los controles y colocarlos en paralelo.  
  
3.  En el menú **Datos**, haga clic en **Mostrar orígenes de datos**.  
  
    > [!NOTE]
    >  Si la ventana **Orígenes de datos** está vacía, agréguele un origen de datos.  Para obtener más información, vea [Información general sobre orígenes de datos](/visual-studio/data-tools/add-new-data-sources).  
  
4.  En la ventana **Orígenes de datos**, seleccione el nodo de nivel superior de la tabla principal.  
  
5.  Cambie el tipo de colocación de la tabla principal a Detalles haciendo clic en **Detalles** en la lista desplegable del nodo de tabla.  
  
6.  Arrastre el nodo de tabla principal a la región de la plantilla de elementos del primer control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
7.  Expanda el nodo de tabla principal y seleccione el nodo de detalle de la tabla relacionada.  
  
8.  Cambie el tipo de colocación de la tabla de detalle a Detalles haciendo clic en **Detalles** en la lista desplegable del nodo de la tabla.  
  
9. Seleccione este nodo de tabla y arrástrelo a la región de plantilla de elementos del segundo control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Cómo: Mostrar los datos enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [Cómo: Mostrar datos relacionados en una aplicación de Windows Forms](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md)   
 [Cómo: Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
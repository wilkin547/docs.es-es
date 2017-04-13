---
title: "Compatibilidad para las nuevas caracter&#237;sticas de Workflow Foundation 4.5 en el dise&#241;ador de flujo de trabajo rehospedado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1a4a4038-d8e6-41dd-99ea-93bd76286772
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Compatibilidad para las nuevas caracter&#237;sticas de Workflow Foundation 4.5 en el dise&#241;ador de flujo de trabajo rehospedado
[!INCLUDE[wf](../../../includes/wf-md.md)] en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] presentó muchas características nuevas, incluidas varias mejoras en la experiencia de diseñador de flujo de trabajo.En este tema se detallan las características admitidas en el diseñador rehospedado y las que no se admiten.  
  
> [!NOTE]
>  Para obtener una lista de todas las nuevas características de [!INCLUDE[wf](../../../includes/wf-md.md)] presentadas en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], incluidas las que no están relacionadas con el rehospedaje de diseñador, vea [Novedades de Windows Workflow Foundation en .NET 4.5](../../../docs/framework/windows-workflow-foundation//whats-new-in-wf-in-dotnet.md).  
  
## Actividades  
 La biblioteca integrada de actividades contiene nuevas actividades y características para las actividades existentes.Todas estas nuevas actividades se admiten en el diseñador rehospedado.Para obtener más información acerca de estas nuevas actividades, vea la sección [Actividades](../../../docs/framework/windows-workflow-foundation//whats-new-in-wf-in-dotnet.md#BKMK_NewActivities) de [Novedades de Windows Workflow Foundation en .NET 4.5](../../../docs/framework/windows-workflow-foundation//whats-new-in-wf-in-dotnet.md).  
  
## Expresiones de C\#  
 Antes de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], todas las expresiones de flujos de trabajo solo se podían escribir en Visual Basic.En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], las expresiones de Visual Basic solo se usan para los proyectos creados con Visual Basic.Los proyectos de Visual C\# ahora usan C\# para expresiones.Al crear flujos de trabajo en [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], se proporciona un editor de expresiones de C\# totalmente funcional con capacidades tales como resaltado de gramática e IntelliSense.Seguirán funcionando los proyectos de flujo de trabajo de C\# creados en versiones anteriores que usan expresiones de Visual Basic.  
  
> [!WARNING]
>  Las expresiones de C\# no se admiten en el diseñador rehospedado.  
  
## Nuevas capacidades de diseñador  
  
### Búsqueda de diseñador  
 Las características [Búsqueda rápida](../../../docs/framework/windows-workflow-foundation//whats-new-in-wf-in-dotnet.md#BKMK_QuickFind) y [Buscar en archivos](../../../docs/framework/windows-workflow-foundation//whats-new-in-wf-in-dotnet.md#BKMK_FindInFiles) presentadas con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] no se admiten en el diseñador rehospedado.La búsqueda de `Toolbox` se admite en el diseñador rehospedado.Para obtener más información acerca de estas características, vea [Búsqueda de diseñador](../../../docs/framework/windows-workflow-foundation//whats-new-in-wf-in-dotnet.md#BKMK_DesignerSearch).  
  
> [!WARNING]
>  Las opciones [Búsqueda rápida](../../../docs/framework/windows-workflow-foundation//whats-new-in-wf-in-dotnet.md#BKMK_QuickFind) y [Buscar en archivos](../../../docs/framework/windows-workflow-foundation//whats-new-in-wf-in-dotnet.md#BKMK_FindInFiles) no se admiten en el diseñador rehospedado.  
  
### Eliminar un elemento del menú contextual en el diseñador de variables y argumentos  
 En [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], las variables y los argumentos solo se podían eliminar en el diseñador con el teclado.A partir de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], las variables y los argumentos se pueden eliminar mediante el menú contextual.Esta característica se admite en el diseñador rehospedado.  
  
 En la captura de pantalla siguiente se muestra el menú contextual del diseñador de variables y argumentos.  
  
 ![Menú contextual del diseñador de variables y argumentos](../../../docs/framework/windows-workflow-foundation//media/designercontextmenu.png "DesignerContextMenu")  
  
### Rodear de forma automática con secuencia  
 Debido a que un flujo de trabajo o determinadas actividades de contenedor \(como <xref:System.Activities.Statements.NoPersistScope>\) solo pueden contener una única actividad de cuerpo, para agregar una segunda actividad el desarrollador tenía que eliminar la primera actividad, agregar una actividad <xref:System.Activities.Statements.Sequence> y, a continuación, agregar ambas actividades a la actividad de secuencia.A partir de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], al agregar una segunda actividad a la superficie del diseñador, se creará una actividad `Sequence` automáticamente para incluir ambas actividades.Esta característica se admite en el diseñador rehospedado.  
  
 La captura de pantalla siguiente muestra una actividad `WriteLine` en `Body` de `NoPersistScope`.  
  
 ![Rodear de forma automática la ubicación de destino](../../../docs/framework/windows-workflow-foundation//media/autosurround1.png "AutoSurround1")  
  
 La captura de pantalla siguiente muestra la actividad `Sequence` creada automáticamente en `Body` cuando se coloca un segundo elemento `WriteLine` debajo del primero.  
  
 ![Actividad Sequence creada automáticamente](../../../docs/framework/windows-workflow-foundation//media/autosurround2.png "AutoSurround2")  
  
### Modo panorámico  
 Para navegar con mayor facilidad en un flujo de trabajo grande en el diseñador, se puede habilitar el modo panorámico, lo que permite al desarrollador hacer clic y arrastrar para mover la parte visible del flujo de trabajo, en lugar de tener que usar las barras de desplazamiento.El botón para activar el modo panorámico está en la esquina inferior derecha del diseñador.Esta característica se admite en el diseñador rehospedado.  
  
 En la captura de pantalla siguiente se muestra el botón de panorámica que se encuentra en la esquina inferior derecha del diseñador de flujo de trabajo.  
  
 ![Botón de panorámica en el Diseñador de flujo de trabajo](../../../docs/framework/windows-workflow-foundation//media/panbutton.png "PanButton")  
  
 El botón central del mouse o la barra espaciadora también se pueden usar para aplicar la panorámica al diseñador de flujo de trabajo.  
  
### Selección múltiple  
 Se pueden seleccionar varias actividades al mismo tiempo; para ello, se arrastra un rectángulo alrededor de ellas \(cuando no se ha habilitado el modo panorámico\) o manteniendo presionada la tecla CTRL y se hace clic en las actividades deseadas una por una.Esta característica se admite en el diseñador rehospedado.  
  
 Asimismo, se pueden arrastrar y colocar en el diseñador selecciones múltiples de actividad, y también se puede interactuar con ellas mediante el menú contextual.  
  
### Vista de esquema de los elementos de flujo de trabajo  
 Para que sea más fácil navegar en los flujos de trabajo jerárquicos, los componentes de un flujo de trabajo se muestran en una vista de esquema de árbol.La vista de esquema se muestra en la vista **Esquema del documento**.Para abrir esta vista en [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], desde el menú superior, seleccione **Vista**, **Otras ventanas**, **Esquema del documento** o presione Ctrl W, U.Al hacer clic en un nodo en la vista de esquema navegará a la actividad correspondiente en el diseñador de flujo de trabajo, y la vista de esquema se actualizará para mostrar las actividades seleccionadas en el diseñador.Esta característica se admite en el diseñador rehospedado.  
  
 La captura de pantalla siguiente del flujo de trabajo completado de [Tutorial de introducción](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md) muestra la vista de esquema con un flujo de trabajo secuencial.  
  
 ![Vista Esquema en el Diseñador de flujo de trabajo](../../../docs/framework/windows-workflow-foundation//media/outlineviewinworkflowdesigner.jpg "OutlineViewinWorkflowDesigner")  
  
### Más control de la visibilidad de los elementos de barra y de encabezado de shell  
 En un diseñador rehospedado, algunos de los controles estándar de la interfaz de usuario pueden no tener significado para un flujo de trabajo determinado y se pueden desactivar.En [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], solo la barra de shell de la parte inferior del diseñador admite esta personalización.En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], la visibilidad de los elementos de encabezado de shell en la parte superior del diseñador puede ajustarse si se establece <xref:System.Activities.Presentation.View.DesignerView.WorkflowShellHeaderItemsVisibility%2A> con el valor adecuado de <xref:System.Activities.Presentation.View.ShellHeaderItemsVisibility>.  
  
### Conexión e inserción automáticas en flujos de trabajo de diagrama de flujo y de máquina de estados  
 En [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], las conexiones entre los nodos de un flujo de trabajo de diagrama de flujo tenían que agregarse manualmente.En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], los nodos de diagrama de flujo y de máquina de estados tienen puntos de conexión automática que se hacen visibles cuando se arrastra una actividad del cuadro de herramientas a la superficie del diseñador.Al colocar una actividad en uno de estos puntos se agrega automáticamente la actividad junto con la conexión necesaria.  
  
 La captura de pantalla siguiente muestra los puntos de unión que se hacen visibles cuando se arrastra una actividad desde el cuadro de herramientas.  
  
 ![Nodo inicial del diagrama de flujo que muestra puntos de conexión automática](../../../docs/framework/windows-workflow-foundation//media/autoconnect1.png "Autoconnect1")  
  
 Las actividades también se pueden arrastrar a las conexiones entre los nodos y estados de un diagrama de flujo para insertar automáticamente el nodo entre otros dos nodos.La captura de pantalla siguiente muestra la línea de conexión resaltada donde se pueden arrastrar y colocar actividades del cuadro de herramientas.  
  
 ![Controlador de inserción automática para colocar actividades](../../../docs/framework/windows-workflow-foundation//media/autoinsert.png "Autoinsert")  
  
 La conexión y la inserción automáticas se admiten en el diseñador rehospedado.  
  
### Anotaciones del diseñador  
 Para facilitar el desarrollo de flujos de trabajo de mayor tamaño, el diseñador admite ahora agregar anotaciones para ayudar a realizar el seguimiento del proceso de diseño.Se pueden agregar anotaciones a actividades, estados, nodos del diagrama de flujo, variables y argumentos.En la captura de pantalla siguiente se muestra el menú contextual usado para agregar anotaciones al diseñador.  
  
 ![Menú contextual de la anotación](../../../docs/framework/windows-workflow-foundation//media/annotationdialog.png "annotationdialog")  
  
 Las anotaciones de diseñador se admiten en el diseñador rehospedado.  
  
### Definir y usar objetos ActivityDelegate en el diseñador  
 Las actividades de [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] usaban objetos <xref:System.Activities.ActivityDelegate> para exponer puntos de ejecución donde otras partes del flujo de trabajo podían interactuar con la ejecución de un flujo de trabajo, pero para usar estos puntos de ejecución a menudo era necesaria una cantidad de código considerable.En esta versión, los desarrolladores pueden definir y usar delegados de actividad mediante el diseñador de flujo de trabajo.Para obtener más información, vea [Definir y consumir delegados de actividad en el Diseñador de flujo de trabajo](../Topic/How%20to:%20Define%20and%20consume%20activity%20delegates%20in%20the%20Workflow%20Designer.md).  
  
 Los delegados de actividad se admiten en el diseñador rehospedado.  
  
### Validación en tiempo de compilación  
 En [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], los errores de validación del flujo de trabajo no se contaban como errores de compilación durante la compilación de un proyecto de flujo de trabajo.Esto significaba que la compilación de un proyecto de flujo de trabajo podía realizarse correctamente aunque hubiera errores de validación del flujo de trabajo.En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], los errores de validación del flujo de trabajo provocan un error en la compilación.  
  
> [!WARNING]
>  La validación en tiempo de compilación no se admite en el diseñador rehospedado.  
  
### Validación en segundo plano en tiempo de diseño  
 En [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], los flujos de trabajo se validaban como un proceso en primer plano, lo que podría hacer que la interfaz de usuario no respondiera durante un proceso de validación complejo o largo.La validación del flujo de trabajo ahora tiene lugar en un subproceso de fondo, para no bloquear la interfaz de usuario.  
  
 La validación en segundo plano en tiempo de diseño se admite en el diseñador rehospedado.  
  
### El estado de la vista se encuentra en una ubicación diferente en archivos XAML  
 En [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], la información de estado de la vista para un flujo de trabajo se almacena en el archivo XAML en muchas ubicaciones diferentes.Esto es un problema para los desarrolladores que desean leer directamente XAML o escribir código para quitar la información de estado de la vista.En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], la información de estado de la vista en el archivo XAML se serializa como un elemento independiente en dicho archivo. Los desarrolladores pueden buscar y editar fácilmente la información de estado de la vista de una actividad o quitar el estado de la vista.  
  
 Esta característica se admite en el diseñador de flujo de trabajo rehospedado.  
  
### Habilitación de las características de flujo de trabajo 4.5 en el diseñador rehospedado  
 Para mantener la compatibilidad con versiones anteriores, algunas características nuevas incluidas en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] no están habilitadas de forma predeterminada en el diseñador rehospedado.Esto sirve para asegurarse de que las aplicaciones existentes que usan el diseñador rehospedado no dejen de funcionar por la actualización a la versión más reciente.Para habilitar las nuevas características en el diseñador rehospedado, establezca <xref:System.Activities.Presentation.DesignerConfigurationService.TargetFrameworkName%2A> en ".Net Framework 4.5" o establezca miembros individuales de <xref:System.Activities.Presentation.DesignerConfigurationService> para habilitar características individuales.  
  
## Nuevos modelos de desarrollo de flujo de trabajo  
 Además de los modelos de desarrollo de flujo de trabajo de diagrama de flujo y secuenciales, esta versión incluye flujos de trabajo de máquina de estados y servicios de flujo de trabajo de contrato primero.  
  
### Flujos de trabajo de máquina de estados  
 Los flujos de trabajo de máquina de estados se incluyeron como parte de .NET Framework 4.0.1 en la [Actualización 1 de la plataforma Microsoft .NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=215092).Esta actualización incluía varias clases y actividades nuevas que permitían a los desarrolladores crear flujos de trabajo de máquina de estados.Estas clases y actividades se han actualizado para [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].Las actualizaciones incluyen:  
  
1.  Capacidad de establecer puntos de interrupción en estados  
  
2.  Capacidad de copiar y pegar transiciones en el diseñador de flujo de trabajo  
  
3.  Compatibilidad del diseñador para la creación de transiciones de desencadenador compartidas  
  
4.  Actividades usadas para crear flujos de trabajo de máquina de estados, incluidas: <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State> y <xref:System.Activities.Statements.Transition>  
  
 La captura de pantalla siguiente muestra el flujo de trabajo de máquina de estados completado del paso [Crear un flujo de trabajo de máquina de estados](../../../docs/framework/windows-workflow-foundation//how-to-create-a-state-machine-workflow.md) de [Tutorial de introducción](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md).  
  
 ![Flujo de trabajo de máquina de estados completado](../../../docs/framework/windows-workflow-foundation//media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")  
  
 Para obtener más información sobre cómo crear flujos de trabajo de máquina de estados, vea [Flujos de trabajo de máquina de estados](../../../docs/framework/windows-workflow-foundation//state-machine-workflows.md).Los flujos de trabajo de máquina de estados se admiten en el diseñador rehospedado.  
  
### Desarrollo de flujo de trabajo de contrato primero  
 La herramienta de desarrollo del flujo de trabajo de contrato primero permite al desarrollador diseñar un contrato en Code First y, a continuación, haciendo algunos clics en [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], generar automáticamente una plantilla de actividad en el cuadro de herramientas que representa cada operación.Estas actividades se usan para crear un flujo de trabajo que implemente las operaciones definidas por el contrato.El diseñador de flujo de trabajo validará el servicio de flujo de trabajo para garantizar que estas operaciones se implementan y la signatura del flujo de trabajo coincide con la signatura del contrato.El desarrollador también puede asociar un servicio de flujo de trabajo a una colección de contratos implementados.Para obtener más información sobre el desarrollo de servicios de flujo de trabajo de contrato primero, vea [Crear un servicio de flujo de trabajo que consuma un contrato de servicio existente](../../../docs/framework/windows-workflow-foundation//how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md).  
  
> [!WARNING]
>  El desarrollo de flujo de trabajo de contrato primero no se admite en el diseñador de flujo de trabajo.
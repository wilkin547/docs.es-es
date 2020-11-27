---
title: Compatibilidad para las nuevas características de Workflow Foundation 4.5 en el diseñador de flujo de trabajo rehospedado
ms.date: 03/30/2017
ms.assetid: 1a4a4038-d8e6-41dd-99ea-93bd76286772
ms.openlocfilehash: 139215131afa38bc33539fa242a3584eb67d7941
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293954"
---
# <a name="support-for-new-workflow-foundation-45-features-in-the-rehosted-workflow-designer"></a>Compatibilidad para las nuevas características de Workflow Foundation 4.5 en el diseñador de flujo de trabajo rehospedado

Windows Workflow Foundation (WF) en .NET Framework 4,5 presentó muchas características nuevas, incluidas varias mejoras en la experiencia del diseñador de flujo de trabajo. En este tema se detallan las características admitidas en el diseñador rehospedado y las que no se admiten.

> [!NOTE]
> Para obtener una lista de todas las nuevas características de Windows Workflow Foundation (WF) introducidas en .NET Framework 4,5, incluidas las que no están relacionadas con el rehost del diseñador, consulte [novedades de Windows Workflow Foundation en .NET Framework 4,5](whats-new-in-wf-in-dotnet.md).

## <a name="activities"></a>Actividades

 La biblioteca integrada de actividades contiene nuevas actividades y características para las actividades existentes. Todas estas nuevas actividades se admiten en el diseñador rehospedado. Para obtener más información sobre estas nuevas actividades, vea la sección [actividades](whats-new-in-wf-in-dotnet.md#BKMK_NewActivities) de [novedades de Windows Workflow Foundation en .NET Framework 4,5](whats-new-in-wf-in-dotnet.md).

## <a name="c-expressions"></a>Expresiones de C#

 Antes de .NET Framework 4,5, todas las expresiones de los flujos de trabajo solo se podían escribir en Visual Basic. En .NET Framework 4,5, las expresiones de Visual Basic solo se usan para los proyectos creados con Visual Basic. Los proyectos de Visual C# ahora usan C# para expresiones. Al crear flujos de trabajo en Visual Studio 2012, se proporciona un editor de expresiones de C# totalmente funcional con capacidades como resaltado de gramática e IntelliSense. Seguirán funcionando los proyectos de flujo de trabajo de C# creados en versiones anteriores que usan expresiones de Visual Basic.

> [!WARNING]
> Las expresiones de C# no se admiten en el diseñador rehospedado.

## <a name="new-designer-capabilities"></a>Nuevas capacidades de diseñador

### <a name="designer-search"></a>Búsqueda de diseñador

 Las características de [búsqueda rápida](whats-new-in-wf-in-dotnet.md#BKMK_QuickFind) y [búsqueda en archivos](whats-new-in-wf-in-dotnet.md#BKMK_FindInFiles) introducidas con .NET Framework 4,5 no se admiten en el diseñador rehospedado. La búsqueda de `Toolbox` se admite en el diseñador rehospedado. Para obtener más información sobre estas características, vea búsqueda en el [Diseñador](whats-new-in-wf-in-dotnet.md#BKMK_DesignerSearch).

> [!WARNING]
> La [búsqueda rápida](whats-new-in-wf-in-dotnet.md#BKMK_QuickFind) y la [búsqueda en archivos](whats-new-in-wf-in-dotnet.md#BKMK_FindInFiles) no se admiten en el diseñador rehospedado.

### <a name="delete-context-menu-item-in-variable-and-argument-designer"></a>Eliminar un elemento del menú contextual en el diseñador de variables y argumentos

 En .NET Framework 4, las variables y los argumentos solo se pueden eliminar en el diseñador con el teclado. A partir de .NET Framework 4,5, las variables y los argumentos se pueden eliminar mediante el menú contextual. Esta característica se admite en el diseñador rehospedado.

 En la captura de pantalla siguiente se muestra el menú contextual del diseñador de variables y argumentos.

 ![Menú contextual del diseñador de variables y argumentos](./media/wf-features-in-the-rehosted-workflow-designer/designer-context-menu.png)

### <a name="auto-surround-with-sequence"></a>Rodear de forma automática con secuencia

 Debido a que un flujo de trabajo o determinadas actividades de contenedor (como <xref:System.Activities.Statements.NoPersistScope>) solo pueden contener una única actividad de cuerpo, para agregar una segunda actividad el desarrollador tenía que eliminar la primera actividad, agregar una actividad <xref:System.Activities.Statements.Sequence> y, a continuación, agregar ambas actividades a la actividad de secuencia. A partir de .NET Framework 4,5, al agregar una segunda actividad a la superficie del diseñador, se `Sequence` creará automáticamente una actividad para ajustar ambas actividades. Esta característica se admite en el diseñador rehospedado.

 La captura de pantalla siguiente muestra una actividad `WriteLine` en `Body` de `NoPersistScope`.

 ![Una actividad WriteLine en el cuerpo de una actividad NoPersistScope.](./media/wf-features-in-the-rehosted-workflow-designer/auto-surround-write-line-activity.png)

 La captura de pantalla siguiente muestra la actividad `Sequence` creada automáticamente en `Body` cuando se coloca un segundo elemento `WriteLine` debajo del primero.

 ![Secuencia creada automáticamente en el cuerpo de un NoPersistScope.](./media/wf-features-in-the-rehosted-workflow-designer/auto-surround-sequence-activity.png)

### <a name="pan-mode"></a>Modo panorámico

 Para navegar con mayor facilidad en un flujo de trabajo grande en el diseñador, se puede habilitar el modo panorámico, lo que permite al desarrollador hacer clic y arrastrar para mover la parte visible del flujo de trabajo, en lugar de tener que usar las barras de desplazamiento. El botón para activar el modo panorámico está en la esquina inferior derecha del diseñador. Esta característica se admite en el diseñador rehospedado.

 En la captura de pantalla siguiente se muestra el botón de panorámica que se encuentra en la esquina inferior derecha del diseñador de flujo de trabajo.

 ![Botón de panorámica resaltado en el diseñador de flujo de trabajo.](./media/wf-features-in-the-rehosted-workflow-designer/pan-button-workflow-designer.png)

 El botón central del mouse o la barra espaciadora también se pueden usar para aplicar la panorámica al diseñador de flujo de trabajo.

### <a name="multi-select"></a>Selección múltiple

 Se pueden seleccionar varias actividades al mismo tiempo; para ello, se arrastra un rectángulo alrededor de ellas (cuando no se ha habilitado el modo panorámico) o manteniendo presionada la tecla CTRL y se hace clic en las actividades deseadas una por una. Esta característica se admite en el diseñador rehospedado.

 Asimismo, se pueden arrastrar y colocar en el diseñador selecciones múltiples de actividad, y también se puede interactuar con ellas mediante el menú contextual.

### <a name="outline-view-of-workflow-items"></a>Vista de esquema de los elementos de flujo de trabajo

 Para que sea más fácil navegar en los flujos de trabajo jerárquicos, los componentes de un flujo de trabajo se muestran en una vista de esquema de árbol. La vista de esquema se muestra en la vista **esquema del documento** . Para abrir esta vista en Visual Studio, en el menú superior, seleccione **vista**, **otras ventanas**, **esquema del documento** o presione Ctrl W, U. Al hacer clic en un nodo en la vista de esquema navegará a la actividad correspondiente en el diseñador de flujo de trabajo, y la vista de esquema se actualizará para mostrar las actividades seleccionadas en el diseñador. Esta característica se admite en el diseñador rehospedado.

 La captura de pantalla siguiente del flujo de trabajo completado en el [Introducción tutorial](getting-started-tutorial.md) muestra la vista de esquema con un flujo de trabajo secuencial.

 ![Captura de pantalla de la vista de esquema con un flujo de trabajo secuencial en Visual Studio](./media/wf-features-in-the-rehosted-workflow-designer/outline-view-in-workflow-designer.jpg)

### <a name="more-control-of-visibility-of-shell-bar-and-header-items"></a>Más control de la visibilidad de los elementos de barra y de encabezado de shell

 En un diseñador rehospedado, algunos de los controles estándar de la interfaz de usuario pueden no tener significado para un flujo de trabajo determinado y se pueden desactivar. En .NET Framework 4, esta personalización solo es compatible con la barra de Shell en la parte inferior del diseñador. En .NET Framework 4,5, la visibilidad de los elementos de encabezado del shell en la parte superior del diseñador se puede ajustar estableciendo <xref:System.Activities.Presentation.View.DesignerView.WorkflowShellHeaderItemsVisibility%2A> con el <xref:System.Activities.Presentation.View.ShellHeaderItemsVisibility> valor adecuado.

### <a name="auto-connect-and-auto-insert-in-flowchart-and-state-machine-workflows"></a>Conexión e inserción automáticas en flujos de trabajo de diagrama de flujo y de máquina de estados

 En .NET Framework 4, las conexiones entre los nodos de un flujo de trabajo de diagrama de flujo tenían que agregarse manualmente. En .NET Framework 4,5, los nodos de diagrama de flujo y de máquina de Estados tienen puntos de conexión automática que se hacen visibles cuando se arrastra una actividad desde el cuadro de herramientas hasta la superficie del diseñador. Al colocar una actividad en uno de estos puntos se agrega automáticamente la actividad junto con la conexión necesaria.

 La captura de pantalla siguiente muestra los puntos de unión que se hacen visibles cuando se arrastra una actividad desde el cuadro de herramientas.

 ![Nodo de inicio del diagrama de flujo que muestra puntos de conexión automática](./media/wf-features-in-the-rehosted-workflow-designer/auto-connect-points-start-node.png)

 Las actividades también se pueden arrastrar a las conexiones entre los nodos y estados de un diagrama de flujo para insertar automáticamente el nodo entre otros dos nodos. La captura de pantalla siguiente muestra la línea de conexión resaltada donde se pueden arrastrar y colocar actividades del cuadro de herramientas.

 ![Controlador de inserción automática para colocar actividades](./media/wf-features-in-the-rehosted-workflow-designer/auto-insert-connecting-line.png)

 La conexión y la inserción automáticas se admiten en el diseñador rehospedado.

### <a name="designer-annotations"></a>Anotaciones del diseñador

 Para facilitar el desarrollo de flujos de trabajo de mayor tamaño, el diseñador admite ahora agregar anotaciones para ayudar a realizar el seguimiento del proceso de diseño. Se pueden agregar anotaciones a actividades, estados, nodos del diagrama de flujo, variables y argumentos. En la captura de pantalla siguiente se muestra el menú contextual usado para agregar anotaciones al diseñador.

 ![Captura de pantalla que muestra el menú para agregar notaciones.](./media/wf-features-in-the-rehosted-workflow-designer/designer-annotations-context-menu.png)

 Las anotaciones de diseñador se admiten en el diseñador rehospedado.

### <a name="define-and-consume-activitydelegate-objects-in-the-designer"></a>Definir y usar objetos ActivityDelegate en el diseñador

 Las actividades de .NET Framework 4 usaban <xref:System.Activities.ActivityDelegate> objetos para exponer puntos de ejecución donde otras partes del flujo de trabajo podían interactuar con la ejecución de un flujo de trabajo, pero el uso de estos puntos de ejecución normalmente requerían una cantidad de código justa. En esta versión, los desarrolladores pueden definir y usar delegados de actividad mediante el diseñador de flujo de trabajo. Para obtener más información, vea [Cómo: definir y usar delegados de actividad en el diseñador de flujo de trabajo](/visualstudio/workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer).

 Los delegados de actividad se admiten en el diseñador rehospedado.

### <a name="build-time-validation"></a>Validación en tiempo de compilación

 En .NET Framework 4, los errores de validación de flujo de trabajo no se cuentan como errores de compilación durante la compilación de un proyecto de flujo de trabajo. Esto significaba que la compilación de un proyecto de flujo de trabajo podía realizarse correctamente aunque hubiera errores de validación del flujo de trabajo. En .NET Framework 4,5, los errores de validación de flujo de trabajo provocan un error en la compilación.

> [!WARNING]
> La validación en tiempo de compilación no se admite en el diseñador rehospedado.

### <a name="design-time-background-validation"></a>Validación en segundo plano en tiempo de diseño

 En .NET Framework 4, los flujos de trabajo se validan como un proceso en primer plano, lo que podría bloquear la interfaz de usuario durante procesos de validación complejos o que consumen mucho tiempo. La validación del flujo de trabajo ahora tiene lugar en un subproceso de fondo, para no bloquear la interfaz de usuario.

 La validación en segundo plano en tiempo de diseño se admite en el diseñador rehospedado.

### <a name="view-state-located-in-a-separate-location-in-xaml-files"></a>El estado de la vista se encuentra en una ubicación diferente en archivos XAML

 En .NET Framework 4, la información de estado de vista de un flujo de trabajo se almacena en el archivo XAML en muchas ubicaciones diferentes. Esto es un problema para los desarrolladores que desean leer directamente XAML o escribir código para quitar la información de estado de la vista. En .NET Framework 4,5, la información de estado de la vista en el archivo XAML se serializa como un elemento independiente en el archivo XAML.  Los desarrolladores pueden encontrar y editar fácilmente la información de estado de vista de una actividad, o bien quitar el estado de vista por completo.

 Esta característica se admite en el diseñador de flujo de trabajo rehospedado.

### <a name="opt-in-for-workflow-45-features-in-rehosted-designer"></a>Habilitación de las características de flujo de trabajo 4.5 en el diseñador rehospedado

 Para mantener la compatibilidad con versiones anteriores, algunas de las nuevas características incluidas en .NET Framework 4,5 no están habilitadas de forma predeterminada en el diseñador rehospedado. Esto sirve para asegurarse de que las aplicaciones existentes que usan el diseñador rehospedado no dejen de funcionar por la actualización a la versión más reciente. Para habilitar las nuevas características en el diseñador rehospedado, establezca <xref:System.Activities.Presentation.DesignerConfigurationService.TargetFrameworkName%2A> en ".Net Framework 4.5" o establezca miembros individuales de <xref:System.Activities.Presentation.DesignerConfigurationService> para habilitar características individuales.

## <a name="new-workflow-development-models"></a>Nuevos modelos de desarrollo de flujo de trabajo

 Además de los modelos de desarrollo de flujo de trabajo de diagrama de flujo y secuenciales, esta versión incluye flujos de trabajo de máquina de estados y servicios de flujo de trabajo de contrato primero.

### <a name="state-machine-workflows"></a>Flujos de trabajo de máquina de estados

 Los flujos de trabajo de máquina de Estados se introdujeron como parte del .NET Framework 4.0.1 en la [actualización 1 de la plataforma Microsoft .NET Framework 4](/archive/blogs/endpoint/microsoft-net-framework-4-platform-update-1). Esta actualización incluía varias clases y actividades nuevas que permitían a los desarrolladores crear flujos de trabajo de máquina de estados. Estas clases y actividades se han actualizado para .NET Framework 4,5. Las actualizaciones incluyen:

1. Capacidad de establecer puntos de interrupción en estados

2. Capacidad de copiar y pegar transiciones en el diseñador de flujo de trabajo

3. Compatibilidad del diseñador para la creación de transiciones de desencadenador compartidas

4. Actividades usadas para crear flujos de trabajo de máquina de estados, incluidas: <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State> y <xref:System.Activities.Statements.Transition>

 En la captura de pantalla siguiente se muestra el flujo de trabajo de equipo de estado completado en el Introducción paso del [tutorial](getting-started-tutorial.md) [Cómo: crear un flujo de trabajo de equipo de estado](how-to-create-a-state-machine-workflow.md).

 ![Ilustración que muestra el flujo de trabajo de equipo de estado completado.](./media/wf-features-in-the-rehosted-workflow-designer/complete-state-machine-workflow.jpg)

 Para obtener más información sobre la creación de flujos de trabajo de máquina de Estados, consulte [flujos de trabajo de máquina de Estados](state-machine-workflows.md). Los flujos de trabajo de máquina de estados se admiten en el diseñador rehospedado.

### <a name="contract-first-workflow-development"></a>Desarrollo de flujo de trabajo de contrato primero

 La herramienta de desarrollo de flujos de trabajo de contrato primero permite que el desarrollador diseñe primero un contrato en Code y, a continuación, con unos pocos clics en Visual Studio, genera automáticamente una plantilla de actividad en el cuadro de herramientas que representa cada operación. Estas actividades se usan para crear un flujo de trabajo que implemente las operaciones definidas por el contrato. El diseñador de flujo de trabajo validará el servicio de flujo de trabajo para garantizar que estas operaciones se implementan y la signatura del flujo de trabajo coincide con la signatura del contrato. El desarrollador también puede asociar un servicio de flujo de trabajo a una colección de contratos implementados. Para obtener más información sobre el desarrollo de servicios de flujo de trabajo de contrato primero, vea [Cómo: crear un servicio de flujo de trabajo que consuma un contrato de servicio existente](how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md).

> [!WARNING]
> El desarrollo de flujo de trabajo de contrato primero no se admite en el diseñador de flujo de trabajo.

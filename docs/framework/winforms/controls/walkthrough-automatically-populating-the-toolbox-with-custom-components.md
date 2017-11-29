---
title: "Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 691487046e2a34dbf233dc4bc03e20f9ec245da1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a>Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados
Si los componentes están definidos en un proyecto de la solución actualmente abierta, estas aparecerán automáticamente en el **cuadro de herramientas**, sin ninguna acción necesaria por parte del usuario. Puede rellenar manualmente el **cuadro de herramientas** con componentes personalizados mediante el uso de la [elegir Toolbox Items Dialog Box (Visual Studio)](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb), pero la **cuadro de herramientas** tiene en cuenta de elementos de la solución generar resultados con todas las características siguientes:  
  
-   Implementa <xref:System.ComponentModel.IComponent>;  
  
-   No tiene <xref:System.ComponentModel.ToolboxItemAttribute> establecido en `false`;  
  
-   No tiene <xref:System.ComponentModel.DesignTimeVisibleAttribute> establecido en `false`.  
  
> [!NOTE]
>  El **cuadro de herramientas** no sigue las cadenas de referencia, por lo que no se mostrarán los elementos que no se compilan en un proyecto de la solución.  
  
 Este tutorial muestra cómo un componente personalizado aparece automáticamente en el **cuadro de herramientas** una vez que se basa el componente. Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear un proyecto de formularios Windows Forms.  
  
-   Crear un componente personalizado.  
  
-   Crear una instancia de un componente personalizado.  
  
-   Descargar y volver a cargar un componente personalizado.  
  
 Cuando haya terminado, verá que el **cuadro de herramientas** se rellena con un componente que ha creado.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
1.  Cree un proyecto de aplicación basada en Windows llamado `ToolboxExample`.  
  
     Para obtener más información, consulta [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Agregue un nuevo componente al proyecto. Llámelo `DemoComponent`.  
  
     Para obtener más información, consulte [NIB: Cómo: agregar nuevos elementos de proyecto](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).  
  
3.  Compile el proyecto.  
  
4.  Desde el **herramientas** menú, haga clic en el **opciones** elemento. Haga clic en **General** en el **Diseñador de Windows Forms** de elemento y asegúrese de que el **AutoToolboxPopulate** opción está establecida en **True**.  
  
## <a name="creating-an-instance-of-a-custom-component"></a>Crear una instancia de un componente personalizado  
 El siguiente paso es crear una instancia del componente personalizado en el formulario. Dado que la **cuadro de herramientas** automáticamente las cuentas para el componente nuevo, esto es tan fácil como crear cualquier otro componente o control.  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a>Para crear una instancia de un componente personalizado  
  
1.  Abra el formulario del proyecto en el **Diseñador de formularios**.  
  
2.  En el **cuadro de herramientas**, haga clic en la nueva ficha denominada **Componentes ToolboxExample**.  
  
     Una vez que haga clic en la pestaña, verá **DemoComponent**.  
  
    > [!NOTE]
    >  Por motivos de rendimiento, los componentes en el área rellena automáticamente de la **cuadro de herramientas** no se muestran los mapas de bits personalizados y el <xref:System.Drawing.ToolboxBitmapAttribute> no se admite. Para mostrar un icono para un componente personalizado en el **cuadro de herramientas**, use la **elegir elementos del cuadro de herramientas** cuadro de diálogo para cargar el componente.  
  
3.  Arrastre el componente al formulario.  
  
     Se crea una instancia del componente y se agrega a la **Bandeja de componentes**.  
  
## <a name="unloading-and-reloading-a-custom-component"></a>Descargar y volver a cargar un componente personalizado  
 El **cuadro de herramientas** tiene en cuenta los componentes en cada uno de ellos cargado el proyecto y, cuando se descarga un proyecto, quita las referencias a los componentes del proyecto.  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a>Para experimentar con el efecto en el cuadro de herramientas de descarga y carga de componentes  
  
1.  Descargue el proyecto de la solución.  
  
     Para obtener más información acerca de cómo descargar los proyectos, vea [NIB: Cómo: descargar y volver a cargar proyectos](http://msdn.microsoft.com/en-us/abc0155b-8fcb-4ffc-95b6-698518a7100b). Si se pide que guarde, elija **Sí**.  
  
2.  Agregue un nuevo **aplicación de Windows** proyecto a la solución. Abra el formulario en el **diseñador**.  
  
     El **Componentes ToolboxExample** ficha desde el proyecto anterior es ahora desaparecido.  
  
3.  Volver a cargar el `ToolboxExample` proyecto.  
  
     El **Componentes ToolboxExample** pestaña ahora vuelve a aparecer.  
  
## <a name="next-steps"></a>Pasos siguientes  
 En este tutorial se muestra que la **cuadro de herramientas** tiene en cuenta los componentes de un proyecto, pero la **cuadro de herramientas** es también tiene en cuenta los controles. Experimentar con sus propios controles personalizados agregando y quitando proyectos de control de la solución.  
  
## <a name="see-also"></a>Vea también  
 [General, Diseñador de Windows Forms, cuadro de diálogo Opciones](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834)  
 [Cómo: Manipular las fichas del cuadro de herramientas](http://msdn.microsoft.com/en-us/21285050-cadd-455a-b1f5-a2289a89c4db)  
 [Elegir elementos del cuadro de herramientas (Cuadro de diálogo): Visual Studio](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [Insertar controles en Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)

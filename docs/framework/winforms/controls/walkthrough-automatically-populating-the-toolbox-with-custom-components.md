---
title: 'Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 488d51e748ea17b09e61b982db7abadc34f8e311
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43442803"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a>Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados
Si los componentes están definidos por un proyecto en la solución actualmente abierta, estas aparecerán automáticamente en el **cuadro de herramientas**, con ninguna acción requerida por el usuario. Puede rellenar manualmente el **cuadro de herramientas** con componentes personalizados mediante el uso de la [elegir elementos de cuadro de diálogo) (Visual Studio)](https://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb), pero la **cuadro de herramientas** tiene en cuenta de elementos de la solución de resultados de la compilación con las siguientes características:  
  
-   Implementa <xref:System.ComponentModel.IComponent>;  
  
-   No tiene <xref:System.ComponentModel.ToolboxItemAttribute> establecido en `false`;  
  
-   No tiene <xref:System.ComponentModel.DesignTimeVisibleAttribute> establecido en `false`.  
  
> [!NOTE]
>  El **cuadro de herramientas** no sigue las cadenas de referencia, por lo que no mostrará los elementos que no se compilan en un proyecto de la solución.  
  
 Este tutorial muestra cómo un componente personalizado aparece automáticamente en el **cuadro de herramientas** una vez que se basa el componente. Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear un proyecto de Windows Forms.  
  
-   Creación de un componente personalizado.  
  
-   Creación de una instancia de un componente personalizado.  
  
-   Descarga y carga un componente personalizado.  
  
 Cuando haya terminado, verá que el **cuadro de herramientas** se rellena con un componente que ha creado.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
1.  Cree un proyecto de aplicación basada en Windows llamado `ToolboxExample` (**archivo** > **New** > **proyecto**  >  **Visual C#** o **Visual Basic** > **escritorio clásico de** > **aplicación de Windows Forms**).  
  
2.  Agregue un nuevo componente al proyecto. Llámelo `DemoComponent`.  
  
     Para obtener más información, consulte [NIB: Cómo: agregar nuevos elementos de proyecto](https://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).  
  
3.  Compile el proyecto.  
  
4.  Desde el **herramientas** menú, haga clic en el **opciones** elemento. Haga clic en **General** bajo el **Diseñador de Windows Forms** de elementos y asegúrese de que el **AutoToolboxPopulate** opción está establecida en **True**.  
  
## <a name="creating-an-instance-of-a-custom-component"></a>Creación de una instancia de un componente personalizado  
 El siguiente paso es crear una instancia del componente personalizado en el formulario. Dado que el **cuadro de herramientas** automáticamente cuentas para el componente nuevo, esto es tan fácil como crear cualquier otro componente o control.  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a>Para crear una instancia de un componente personalizado  
  
1.  Abra el formulario del proyecto en el **Diseñador de formularios**.  
  
2.  En el **cuadro de herramientas**, haga clic en la nueva ficha denominada **Componentes ToolboxExample**.  
  
     Al hacer clic en la pestaña, verá **DemoComponent**.  
  
    > [!NOTE]
    >  Por motivos de rendimiento, los componentes en el área rellena automáticamente de la **cuadro de herramientas** no mostrar mapas de bits personalizados y el <xref:System.Drawing.ToolboxBitmapAttribute> no se admite. Para mostrar un icono para un componente personalizado en el **cuadro de herramientas**, utilice el **elegir elementos del cuadro de herramientas** cuadro de diálogo para cargar el componente.  
  
3.  Arrastre el componente al formulario.  
  
     Se crea una instancia del componente y se agrega a la **Bandeja de componentes**.  
  
## <a name="unloading-and-reloading-a-custom-component"></a>Descarga y carga un componente personalizado  
 El **cuadro de herramientas** tiene en cuenta los componentes en cada carga de proyecto y, cuando se descarga un proyecto, se quita las referencias a componentes del proyecto.  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a>Para experimentar con el efecto en el cuadro de herramientas de descarga y carga de componentes  
  
1.  Descargue el proyecto de la solución.  
  
     Para obtener más información sobre cómo descargar los proyectos, vea [NIB: Cómo: descargar y recargar proyectos](https://msdn.microsoft.com/library/abc0155b-8fcb-4ffc-95b6-698518a7100b). Si se le solicite guardar, elija **Sí**.  
  
2.  Agregue un nuevo **aplicación Windows** proyecto a la solución. Abra el formulario en el **diseñador**.  
  
     El **Componentes ToolboxExample** ficha desde el proyecto anterior es ahora han desaparecido.  
  
3.  Volver a cargar el `ToolboxExample` proyecto.  
  
     El **Componentes ToolboxExample** pestaña ahora vuelve a aparecer.  
  
## <a name="next-steps"></a>Pasos siguientes  
 En este tutorial se muestra que el **cuadro de herramientas** tiene en cuenta los componentes de un proyecto, pero la **cuadro de herramientas** es también tiene en cuenta los controles. Experimentar con sus propios controles personalizados mediante la adición y eliminación de proyectos de control de la solución.  
  
## <a name="see-also"></a>Vea también  
 [General, Diseñador de formularios de Windows, cuadro de diálogo Opciones](https://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)  
 [Cómo: Manipular las fichas del cuadro de herramientas](https://msdn.microsoft.com/library/21285050-cadd-455a-b1f5-a2289a89c4db)  
 [Elegir elementos del cuadro de herramientas (Cuadro de diálogo): Visual Studio](https://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [Insertar controles en Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)

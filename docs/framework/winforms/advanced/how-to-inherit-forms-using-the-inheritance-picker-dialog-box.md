---
title: Procedimiento para heredar formularios mediante el cuadro de diálogo Selector de herencia
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], forms
- Inheritance Picker dialog box
- inherited forms [Windows Forms], creating
ms.assetid: 969b4c04-12aa-4297-93a2-0ae747447823
ms.openlocfilehash: 5ae1c236835141b10bc704cd39f55de6e3e974b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723138"
---
# <a name="how-to-inherit-forms-using-the-inheritance-picker-dialog-box"></a>Procedimiento para heredar formularios mediante el cuadro de diálogo Selector de herencia
La forma más sencilla de heredar un formulario u otro objeto es usar el cuadro de diálogo **Selector de herencia**. Con él, puede aprovechar el código o las interfaces de usuario (UI) que ya ha creado en otras soluciones.  
  
> [!NOTE]
>  Para heredar de un formulario con el cuadro de diálogo **Selector de herencia**, el proyecto que contiene el formulario debe haberse compilado en un archivo ejecutable o DLL. Para compilar el proyecto, elija **Compilar solución** en el menú **Compilar**.  
>   
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-windows-form-inherited-from-an-existing-form-by-using-the-inheritance-picker"></a>Para crear un Windows Form heredado de un formulario existente mediante el selector de herencia  
  
1. En el menú **Proyecto**, elija **Agregar Windows Forms**.  
  
     Se abre el cuadro de diálogo **Agregar nuevo elemento**.  
  
2. Búsqueda del **formulario heredado** plantilla desde el control searchbox o haciendo clic en el **Windows Forms** categoría, selecciónela y asígnele un nombre en el **nombre** cuadro. Haga clic en el botón **Agregar** para continuar.  
  
     Se abre el cuadro de diálogo **Selector de herencia**. Si el proyecto actual ya contiene formularios, se muestran en el cuadro de diálogo **Selector de herencia**.  
  
3. Para heredar de un formulario de otro ensamblado, haga clic en el botón **Examinar**.  
  
4. Dentro del cuadro de diálogo **Seleccione un archivo que contenga un componente del que desee heredar**, vaya al proyecto que contiene el formulario o módulo que desea.  
  
5. Haga clic en el nombre del archivo .exe o .dll para seleccionarlo y haga clic en el botón **Abrir**.  
  
     Esto le devuelve al cuadro de diálogo **Selector de herencia**, en cuya lista aparecerá ya el componente junto con el proyecto en el que se encuentra.  
  
6. Seleccione el componente.  
  
     En el **Explorador de soluciones**, el componente se agrega al proyecto. Si tiene una interfaz de usuario, los controles que forman parte del formulario heredado se marcarán con un glifo (![captura de pantalla de los símbolos de herencia de Visual Basic.](./media/how-to-inherit-forms-using-the-inheritance-picker-dialog-box/visual-basic-inheritance-glyph.gif)) y, cuando se seleccione, tendrá un borde que indica el nivel de seguridad que tiene el control en el formulario de superclase. En la tabla siguiente se muestran los comportamientos que se corresponden con los diferentes niveles de seguridad.  
  
    |Nivel de seguridad del control|Interacción disponible mediante el Diseñador y el Editor de código con el formulario heredado|  
    |-------------------------------|--------------------------------------------------------------------------------|  
    |Public|Borde estándar con controladores de tamaño: el control se puede cambiar de tamaño y se puede mover. La clase que declara el control puede acceder al control internamente, y otras clases pueden acceder a él externamente.|  
    |Protegido|Borde estándar con controladores de tamaño: el control se puede cambiar de tamaño y se puede mover. Pueden acceder a él internamente la clase que declara el control y otras clases que heredan de la clase primaria, pero no las clases externas.|  
    |Protected Internal (Protected Friend en Visual Basic)|Borde estándar con controladores de tamaño: el control se puede cambiar de tamaño y se puede mover. Pueden acceder a él internamente la clase que lo declara, cualquier clase que hereda de la clase primaria y otros miembros del ensamblado que lo contiene.|  
    |Internal (Friend en Visual Basic)|Borde estándar sin cuadros de tamaño, se muestra en el formulario, las propiedades son visibles en la ventana **Propiedades**. Sin embargo, todos los aspectos del control se considerarán de solo lectura. El control no se puede mover ni cambiar de tamaño, y tampoco se pueden cambiar sus propiedades. Si el control es un contenedor de otros controles, como un cuadro de grupo, no se pueden agregar nuevos controles y no se pueden quitar los controles existentes, aunque estos controles sean públicos. Solo otros miembros del ensamblado que contiene el control pueden acceder a él.|  
    |Private|Borde estándar sin cuadros de tamaño, se muestra en el formulario, las propiedades son visibles en la ventana **Propiedades**. Sin embargo, todos los aspectos del control se considerarán de solo lectura. El control no se puede mover ni cambiar de tamaño, y tampoco se pueden cambiar sus propiedades. Si el control es un contenedor de otros controles, como un cuadro de grupo, no se pueden agregar nuevos controles y no se pueden quitar los controles existentes, aunque estos controles sean públicos. Solo la clase que declara el control puede acceder a él.|  
  
     Para información sobre de cómo modificar la apariencia de un formulario base, vea [Efectos de modificar la apariencia de un formulario base](effects-of-modifying-base-form-appearance.md).  
  
    > [!NOTE]
    >  Cuando se combinan controles y componentes heredados con controles y componentes estándar de Windows Forms, pueden aparecer conflictos con el orden Z. Para corregirlo, modifique el orden Z; para ello, haga clic en el menú **Formato**, seleccione **Orden** y haga clic en **Traer al frente** o **Enviar al fondo**. Para obtener más información acerca del orden z de los controles, vea [Cómo: Capa de objetos en Windows Forms](../controls/how-to-layer-objects-on-windows-forms.md).  
  
## <a name="see-also"></a>Vea también

- [Inherits (instrucción)](~/docs/visual-basic/language-reference/statements/inherits-statement.md)
- [using](~/docs/csharp/language-reference/keywords/using.md)
- [Efectos de modificar la apariencia de un formulario base](effects-of-modifying-base-form-appearance.md)
- [Herencia visual de Windows Forms](windows-forms-visual-inheritance.md)

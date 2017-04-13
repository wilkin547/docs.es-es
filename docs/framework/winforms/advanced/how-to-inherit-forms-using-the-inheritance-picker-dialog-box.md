---
title: "C&#243;mo: Heredar formularios mediante el cuadro de di&#225;logo Selector de herencia | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "herencia, formularios"
  - "Selector de herencia (cuadro de diálogo)"
  - "formularios heredados, crear"
ms.assetid: 969b4c04-12aa-4297-93a2-0ae747447823
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Heredar formularios mediante el cuadro de di&#225;logo Selector de herencia
La forma más sencilla de heredar un formulario u otro objeto es usar el cuadro de diálogo **Selector de herencia**.  Con él, puede aprovechar el código o las interfaces de usuario \(UI\) que ya ha creado en otras soluciones.  
  
> [!NOTE]
>  Para heredar de un formulario con el cuadro de diálogo **Selector de herencia**, el proyecto que contiene el formulario debe haberse compilado en un archivo ejecutable o DLL.  Para compilar el proyecto, elija **Compilar solución** en el menú **Compilar**.  
>   
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas**.  Para obtener más información, consulte [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para crear un Windows Form heredado de un formulario existente mediante el selector de herencia  
  
1.  En el menú **Proyecto**, elija **Agregar Windows Forms**.  
  
     Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.  
  
2.  Seleccione la plantilla **Formulario heredado** y asígnele un nombre en el cuadro **Nombre**.  Haga clic en el botón **Agregar** para continuar.  
  
     Se abre el cuadro de diálogo **Selector de herencia**.  Si el proyecto actual ya contiene formularios, se muestran en el cuadro de diálogo **Selector de herencia**.  
  
3.  Para heredar de un formulario de otro ensamblado, haga clic en el botón **Examinar**.  
  
4.  Dentro del cuadro de diálogo **Seleccione un archivo que contenga un componente del que desee heredar**, vaya al proyecto que contiene el formulario o módulo que desea.  
  
5.  Haga clic en el nombre del archivo .exe o .dll para seleccionarlo y haga clic en el botón **Abrir**.  
  
     Esto le devuelve al cuadro de diálogo **Selector de herencia**, en cuya lista aparecerá ya el componente junto con el proyecto en el que se encuentra.  
  
6.  Seleccione el componente.  
  
     En el **Explorador de soluciones**, el componente se agrega al proyecto.  Si tiene una interfaz de usuario, los controles que forman parte del formulario heredado se marcarán con un glifo \(![Captura de pantalla de VisualBasicInheritanceSymbol](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.png "vbInheritanceGlyph")\) y, cuando se seleccione, tendrá un borde que indica el nivel de seguridad que el control tiene en el formulario de superclase.  En la tabla siguiente se muestran los comportamientos que se corresponden con los diferentes niveles de seguridad.  
  
    |Nivel de seguridad del control|Interacción disponible mediante el Diseñador y el Editor de código con el formulario heredado|  
    |------------------------------------|---------------------------------------------------------------------------------------------------|  
    |Público|Borde estándar con controladores de tamaño: el control se puede cambiar de tamaño y se puede mover.  La clase que declara el control puede acceder al control internamente, y otras clases pueden acceder a él externamente.|  
    |Protegido|Borde estándar con controladores de tamaño: el control se puede cambiar de tamaño y se puede mover.  Pueden acceder a él internamente la clase que declara el control y otras clases que heredan de la clase primaria, pero no las clases externas.|  
    |Protected Internal \(Protected Friend en Visual Basic\)|Borde estándar con controladores de tamaño: el control se puede cambiar de tamaño y se puede mover.  Pueden acceder a él internamente la clase que lo declara, cualquier clase que hereda de la clase primaria y otros miembros del ensamblado que lo contiene.|  
    |Internal \(Friend en Visual Basic\)|Borde estándar sin cuadros de tamaño, se muestra en el formulario, las propiedades son visibles en la ventana **Propiedades**.  Sin embargo, todos los aspectos del control se considerarán de solo lectura.  El control no se puede mover ni cambiar de tamaño, y tampoco se pueden cambiar sus propiedades.  Si el control es un contenedor de otros controles, como un cuadro de grupo, no se pueden agregar nuevos controles y no se pueden quitar los controles existentes, aunque estos controles sean públicos.  Solo otros miembros del ensamblado que contiene el control pueden acceder a él.|  
    |Privado|Borde estándar sin cuadros de tamaño, se muestra en el formulario, las propiedades son visibles en la ventana **Propiedades**.  Sin embargo, todos los aspectos del control se considerarán de solo lectura.  El control no se puede mover ni cambiar de tamaño, y tampoco se pueden cambiar sus propiedades.  Si el control es un contenedor de otros controles, como un cuadro de grupo, no se pueden agregar nuevos controles y no se pueden quitar los controles existentes, aunque estos controles sean públicos.  Solo la clase que declara el control puede acceder a él.|  
  
     Para obtener información acerca de cómo modificar la apariencia de un formulario base, consulte [Efectos de modificar la apariencia de un formulario base](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md).  
  
    > [!NOTE]
    >  Cuando se combinan controles y componentes heredados con controles y componentes estándar de Windows Forms, pueden aparecer conflictos con el orden Z.  Para corregirlo, modifique el orden Z; para ello, haga clic en el menú **Formato**, seleccione **Orden** y haga clic en **Traer al frente** o **Enviar al fondo**.  Para obtener más información acerca del orden Z de los controles, consulte [Cómo: Disponer objetos en capas en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-layer-objects-on-windows-forms.md).  
  
## Vea también  
 [Inherits \(Instrucción\)](../../../../ocs/visual-basic/language-reference/statements/inherits-statement.md)   
 [utilizar](../Topic/using%20\(C%23%20Reference\).md)   
 [Efectos de modificar la apariencia de un formulario base](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)   
 [Herencia visual de formularios Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
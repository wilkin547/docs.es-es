---
title: "User Input Validation in Windows Forms | Microsoft Docs"
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
  - "Windows Forms, validating user input"
  - "validation, Windows Forms user input"
  - "user input, validating in Windows Forms"
  - "validating user input, Windows Forms"
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# User Input Validation in Windows Forms
Cuando los usuarios especifican datos en la aplicación, quizás desee comprobar que éstos sean válidos antes de que los utilice la aplicación.  Puede exigir que determinados campos de texto no sean de longitud cero, que un campo tenga formato de número telefónico u otro tipo de datos con formato correcto, o que una cadena no contenga caracteres inseguros que pudieran utilizarse para comprometer la seguridad de una base de datos.  Los formularios Windows Forms proporcionan varios métodos para validar la entrada en la aplicación.  
  
## Validación con el control MaskedTextBox  
 Si desea exigir que los usuarios especifiquen datos en un formato bien definido, como un número de teléfono o un número de serie, puede llevarlo a cabo rápidamente y con una mínima cantidad de código mediante el control <xref:System.Windows.Forms.MaskedTextBox>.  Una *máscara* es una cadena formada por caracteres de un lenguaje de enmascaramiento que especifica qué caracteres se pueden especificar en una posición determinada del cuadro de texto.  El control muestra un conjunto de indicadores al usuario.  Si el usuario especifica una entrada incorrecta, por ejemplo, escribe una letra cuando se requiere un dígito, el control rechazará automáticamente la entrada.  
  
 El lenguaje de enmascaramiento que utiliza <xref:System.Windows.Forms.MaskedTextBox> es muy flexible.  Permite especificar caracteres necesarios, opcionales y literales, como guiones y paréntesis, caracteres de divisa y separadores de fechas.  El control también funciona bien cuando se enlaza a un origen de datos.  El evento <xref:System.Windows.Forms.Binding.Format> en un enlace de datos se puede utilizar para dar formato de nuevo a los datos de entrada de modo que cumplan con la máscara, y el evento <xref:System.Windows.Forms.Binding.Parse> puede utilizarse para dar formato de nuevo a los datos de salida de modo que cumplan las especificaciones del campo de datos.  
  
 Para obtener más información, vea [MaskedTextBox \(Control\)](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md).  
  
## Validación orientada a eventos  
 Si desea un control de programación completo sobre la validación o tiene que realizar comprobaciones de validación complejas, utilice los eventos de validación integrados en la mayoría de los controles de formularios Windows Forms.  Cada control que acepta datos proporcionados por el usuario de forma libre tiene un evento <xref:System.Windows.Forms.Control.Validating> que se producirá cada vez que el control requiera la validación de datos.  En el método de control de eventos <xref:System.Windows.Forms.Control.Validating>, puede validar los datos proporcionados por el usuario de varias maneras.  Por ejemplo, si tiene un cuadro de texto que debe contener un código postal, puede realizar la validación mediante los métodos siguientes:  
  
-   Si el código postal debe pertenecer a un grupo de códigos postales concreto, puede realizar una comparación de cadenas en la entrada para validar los datos especificados por el usuario.  Por ejemplo, si el código postal debe estar en el conjunto {10001, 10002, 10003}, puede utilizar una comparación de cadenas para validar los datos.  
  
-   Si el código postal debe estar en un formato concreto puede utilizar expresiones regulares para validar los datos especificados por el usuario.  Por ejemplo, para validar el formato `#####` o `#####-####`, puede utilizar la expresión regular `^(\d{5})(-\d{4})?$`.  Para validar el formato `A#A #A#`, puede utilizar la expresión regular `[A-Z]\d[A-Z] \d[A-Z]\d`.  Para obtener más información sobre las expresiones regulares, vea [Expresiones regulares de .NET Framework](../../../docs/standard/base-types/regular-expressions.md) y [Ejemplos de expresiones regulares](../../../docs/standard/base-types/regular-expression-examples.md).  
  
-   Si el código postal debe ser un código postal de Estados Unidos válido, podría llamar a un servicio Web de códigos postales para validar los datos especificados por el usuario.  
  
 Al evento <xref:System.Windows.Forms.Control.Validating> se le proporciona un objeto de tipo <xref:System.ComponentModel.CancelEventArgs>.  Si determina que los datos del control no son válidos, puede cancelar el evento <xref:System.Windows.Forms.Control.Validating> estableciendo la propiedad <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> de este objeto en `true`.  Si no establece la propiedad <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>, el formulario Windows Forms supondrá que la validación fue correcta para dicho control y desencadenará el evento <xref:System.Windows.Forms.Control.Validated>.  
  
 Para obtener un ejemplo de código que valida una dirección de correo electrónico en <xref:System.Windows.Controls.TextBox>, vea <xref:System.Windows.Forms.Control.Validating>.  
  
### Enlace de datos y validación orientada a eventos  
 La validación resulta de gran utilidad cuando ha enlazado los controles a un origen de datos, por ejemplo una tabla de base de datos.  Con la validación, puede comprobar que los datos del control satisfacen el formato que requiere el origen de datos y que no contienen ningún carácter especial como comillas o barras diagonales inversas que podrían ser inseguras.  
  
 Cuando utiliza el enlace de datos, los datos del control se sincronizan con el origen de datos durante la ejecución del evento <xref:System.Windows.Forms.Control.Validating>.  Si cancela el evento <xref:System.Windows.Forms.Control.Validating>, los datos no se sincronizarán con el origen de datos.  
  
> [!IMPORTANT]
>  Si tiene una validación personalizada que tiene lugar después del evento <xref:System.Windows.Forms.Control.Validating>, no afectará al enlace de datos.  Por ejemplo, si tiene código en un evento <xref:System.Windows.Forms.Control.Validated> que intenta cancelar el enlace de datos, éste aún se producirá.  En este caso, para realizar la validación en el evento <xref:System.Windows.Forms.Control.Validated>, cambie la propiedad **Modo de actualización del origen de datos** del control \(**en \(Enlaces de datos\)**\\**\(Avanzadas\)**\) de **OnValidation** a **Never** y agregue *Control*`.DataBindings["`*\<SUCAMPO\>*`"].WriteValue()` al código de validación.  
  
### Validación implícita y explícita  
 Pero ¿cuándo se validan datos del control?  Esto depende de usted, el desarrollador.  Puede utilizar la validación implícita o explícita, según las necesidades de la aplicación.  
  
#### Validación implícita  
 El enfoque de validación implícita valida los datos según los escribe el usuario.  Puede validar los datos conforme se escriben en un control leyendo las teclas cuando se presionan o, más comúnmente, cada vez que el usuario cambia el foco de entrada de un control y lo traslada al siguiente.  Este enfoque resulta útil si desea ofrecer al usuario información inmediata sobre los datos conforme se procesan.  
  
 Si desea utilizar la validación implícita de un control, debe establecer la propiedad <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> de dicho control en `true`.  Si cancela el evento <xref:System.Windows.Forms.Control.Validating>, el comportamiento del control vendrá determinado por el valor asignado a <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>.  Si asignara <xref:System.Windows.Forms.AutoValidate>, cuando cancele el evento hará que no se produzca el evento <xref:System.Windows.Forms.Control.Validated>.  El foco de entrada permanecerá en el control actual hasta que el usuario cambie los datos a una entrada válida.  Si asignó <xref:System.Windows.Forms.AutoValidate>, no se producirá el evento <xref:System.Windows.Forms.Control.Validated> cuando cancele el evento, pero el foco todavía cambiará al siguiente control.  
  
 Si se asigna <xref:System.Windows.Forms.AutoValidate> a la propiedad <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> se evita la validación implícita en general  Para validar los controles deberá utilizar la validación explícita.  
  
#### Validación explícita  
 El enfoque de validación explícita valida los datos a la vez.  Puede validar los datos en respuesta a una acción del usuario, como hacer clic en un botón Guardar o un vínculo Siguiente.  Cuando se produce la acción del usuario, puede activar la validación explícita mediante una de las siguientes maneras:  
  
-   Llamar a <xref:System.Windows.Forms.ContainerControl.Validate%2A> para validar el último control que ha perdido el foco.  
  
-   Llamar a <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> para validar todos los controles secundarios de un formulario o control contenedor.  
  
-   Llamar a un método personalizado para validar los datos manualmente en los controles.  
  
#### Comportamiento predeterminado de la validación implícita para controles de Windows Forms  
 Los controles de Windows Forms tienen valores predeterminados diferentes para la propiedad <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>.  La tabla siguiente muestra los controles más comunes y sus valores predeterminados.  
  
|Control|Comportamiento de validación predeterminado|  
|-------------|-------------------------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate>|  
|<xref:System.Windows.Forms.PropertyGrid>|Propiedad no expuesta en Visual Studio|  
|<xref:System.Windows.Forms.ToolStripContainer>|Propiedad no expuesta en Visual Studio|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate>|  
  
## Cerrar el formulario y reemplazar la validación  
 Cuando un control conserva el foco porque los datos que contiene no son válidos, es imposible cerrar el formulario primario mediante uno de los métodos usuales:  
  
-   Haciendo clic en el botón **Cerrar**.  
  
-   Seleccionando **Cerrar** en el menú **Sistema**.  
  
-   Llamando al método <xref:System.Windows.Forms.Form.Close%2A> mediante programación.  
  
 Sin embargo, en algunos casos, puede permitir al usuario cerrar el formulario independientemente de que los valores de los controles sean válidos o no.  Puede reemplazar la validación y cerrar un formulario que contenga datos no válidos creando un controlador para el evento <xref:System.Windows.Forms.Form.Closing> del formulario.  En el evento, establezca la propiedad <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> en `false`.  Esto obliga al formulario a cerrarse.  Para obtener más información y un ejemplo, vea <xref:System.Windows.Forms.Form.Closing?displayProperty=fullName>.  
  
> [!NOTE]
>  Si obliga a cerrarse al formulario de esta forma, se perderán los datos de los controles del formulario que no se hayan guardado.  Además, los formularios modales no validan el contenido de los controles cuando se cierran.  Aún puede utilizar la validación de controles para bloquear el foco en un control, pero no tiene que preocuparse por el comportamiento asociado al cierre del formulario.  
  
## Vea también  
 <xref:System.Windows.Forms.Control.Validating?displayProperty=fullName>   
 <xref:System.Windows.Forms.Form.Closing?displayProperty=fullName>   
 <xref:System.ComponentModel.CancelEventArgs?displayProperty=fullName>   
 [MaskedTextBox \(Control\)](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)   
 [Ejemplos de expresiones regulares](../../../docs/standard/base-types/regular-expression-examples.md)
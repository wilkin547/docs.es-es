---
title: "C&#243;mo: Crear controles de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles [Windows Forms], crear"
  - "controles personalizados [Windows Forms], crear"
  - "UserControl (clase), Windows Forms"
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Crear controles de formularios Windows Forms
Un control representa un vínculo gráfico entre el usuario y el programa.  Un control puede proporcionar o procesar datos, aceptar datos proporcionados por el usuario, responder a eventos o ejecutar cualquier otra función que conecte al usuario con la aplicación.  Dado que los controles son básicamente componentes con interfaz gráfica, pueden ejecutar las mismas funciones que realizan los componentes, así como proporcionar interacción con los usuarios.  Los controles se crean con un propósito específico; la creación de controles no es más que una tarea de programación como otra cualquiera.  Teniendo esto en cuenta, los pasos siguientes representan información general sobre el proceso de creación de controles.  Los vínculos proporcionan información adicional acerca de cada paso.  
  
> [!NOTE]
>  Si desea crear un control para utilizarlo en los formularios Web Forms, vea [Developing Custom ASP.NET Server Controls](../Topic/Developing%20Custom%20ASP.NET%20Server%20Controls.md).  
>   
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para crear un control  
  
1.  Determine qué desea que haga el control o qué función desempeñará en la aplicación.  Deberá tener en cuenta los siguientes factores:  
  
    -   ¿Qué clase de interfaz gráfica necesita?  
  
    -   ¿De qué interacciones específicas con el usuario se ocupará este control?  
  
    -   ¿Existe algún control que se aproxime a la funcionalidad que necesita?  
  
    -   ¿Puede obtener la funcionalidad necesaria mediante la combinación de varios controles de formularios Windows Forms?  
  
2.  Si necesita un modelo de objetos para el control, determine cómo se distribuirá la funcionalidad a través del modelo de objetos y divídala entre el control y los objetos secundarios.  Un modelo de objetos puede resultar útil si piensa crear un control complejo o desea incorporar varias funcionalidades.  
  
3.  Determine el tipo de control \(por ejemplo, un control de usuario, un control personalizado, un control heredado de formularios Windows Forms\) que necesita para alcanzar su objetivo.  Para obtener más información, vea [Recomendaciones sobre tipos de controles](../../../../docs/framework/winforms/controls/control-type-recommendations.md) y [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).  
  
4.  Exprese la funcionalidad en forma de propiedades, métodos y eventos del control y sus objetos secundarios o estructuras subsidiarias, y asigne los niveles de acceso adecuados \(por ejemplo, público, protegido, etc.\).  
  
5.  Si necesita que el control utilice una representación personalizada, agregue el código necesario.  Para obtener información detallada, vea [Dibujo y representación personalizados de controles](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
6.  Si el control hereda de <xref:System.Windows.Forms.UserControl>, puede probar su comportamiento en tiempo de ejecución compilando el proyecto de control y ejecutándolo en el **UserControl Test Container**.  Para obtener más información, vea [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
7.  También puede probar y depurar el control creando un nuevo proyecto, como una Aplicación para Windows, y colocándola en un contenedor.  Este proceso se muestra como parte de [Tutorial: Crear un control compuesto con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md).  
  
8.  A medida que agregue las características, agregue nuevas características al proyecto para probarlas.  
  
9. Repita este proceso para refinar el diseño.  
  
10. Empaquete e implemente el control.  Para obtener información detallada, vea [Implementar aplicaciones, servicios y componentes](../Topic/Deploying%20Applications,%20Services,%20and%20Components.md).  
  
## Vea también  
 [Tutorial: Crear un control compuesto con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)   
 [Tutorial: Heredar de un control de formularios Windows Forms con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)   
 [Cómo: Heredar de una clase UserControl](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)   
 [Cómo: Heredar de una clase de control](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)   
 [Cómo: Heredar de controles de formularios Windows Forms existentes](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)   
 [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)   
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
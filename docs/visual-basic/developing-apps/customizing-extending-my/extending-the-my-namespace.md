---
title: "Extender el espacio de nombres My en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.AddingMyExtensions"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My (espacio de nombres)"
  - "My (espacio de nombres), personalizar"
  - "My (espacio de nombres), extender"
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Extender el espacio de nombres My en Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El espacio de nombres `My` de Visual Basic expone las propiedades y los métodos que permiten aprovechar con facilidad la eficacia de .NET Framework.  El espacio de nombres `My` simplifica los problemas de programación comunes y, a menudo, reduce una tarea difícil a una sola línea de código.  Además, el espacio de nombres `My` es totalmente extensible, de modo que se puede personalizar el comportamiento de `My` y agregar los nuevos servicios a su jerarquía para adaptarse a las necesidades concretas de la aplicación.  En este tema se describe cómo personalizar los miembros existentes del espacio de nombres `My` y cómo agregar sus propias clases personalizadas al espacio de nombres `My`.  
  
 **Contenido del tema**  
  
-   [Personalizar miembros existentes del espacio de nombres My](#customizing)  
  
-   [Agregar miembros a Mis objetos](#addingtoobjects)  
  
-   [Agregar objetos personalizados al espacio de nombres My](#addingcustom)  
  
-   [Agregar miembros al espacio de nombres My](#addingtonamespace)  
  
-   [Agregar eventos a objetos My personalizados](#addingevents)  
  
-   [Instrucciones de diseño](#design)  
  
-   [Diseñar bibliotecas de clases para My](#designing)  
  
-   [Empaquetar e implementar extensiones](#packaging)  
  
##  <a name="customizing"></a> Personalizar miembros existentes del espacio de nombres My  
 El espacio de nombres `My` de Visual Basic expone la información usada con frecuencia sobre su aplicación, su equipo, etc.  Para obtener una lista completa de los objetos del espacio de nombres `My`, vea [Referencia de My](../../../visual-basic/language-reference/keywords/my-reference.md).  Quizá sea necesario personalizar los miembros existentes del espacio de nombres `My` para que satisfagan mejor las necesidades de la aplicación.  Se puede establecer en un valor personalizado cualquier propiedad de un objeto del espacio de nombres `My` que no sea de sólo lectura.  
  
 Por ejemplo, suponga que usa frecuentemente el objeto `My.User` para tener acceso al contexto de seguridad actual para el usuario que ejecuta la aplicación.  Sin embargo, su compañía usa un objeto de usuario personalizado a fin de exponer información adicional y funciones para los usuarios.  En este caso, puede reemplazar el valor predeterminado de la propiedad `My.User.CurrentPrincipal` por una instancia de su propio objeto principal personalizado, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbcnExtendingMy#1](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_1.vb)]  
  
 Al establecer la propiedad `CurrentPrincipal` en el objeto `My.User`, se cambia la identidad con la que se ejecuta la aplicación.  El objeto `My.User`, a su vez, devuelve información sobre el usuario recientemente especificado.  
  
##  <a name="addingtoobjects"></a> Agregar miembros a Mis objetos  
 Los tipos devueltos por `My.Application` y `My.Computer` se definen como clases `Partial`.  Por consiguiente, puede extender los objetos `My.Application` y `My.Computer` creando una clase `Partial` denominada `MyApplication` o `MyComputer`.  La clase no puede ser `Private`.  Si especifica la clase como parte del espacio de nombres `My`, puede agregar las propiedades y métodos que se incluirán con los objetos `My.Application` o `My.Computer`.  
  
 Por ejemplo, en el ejemplo siguiente se agrega una propiedad denominada `DnsServerIPAddresses` al objeto `My.Computer`.  
  
 [!code-vb[VbVbcnExtendingMy#2](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_2.vb)]  
  
##  <a name="addingcustom"></a> Agregar objetos personalizados al espacio de nombres My  
 Aunque el espacio de nombres `My` proporciona soluciones para muchas tareas de programación comunes, puede encontrar tareas que el espacio de nombres `My` no resuelve.  Por ejemplo, la aplicación podría obtener acceso a servicios de directorio personalizados para los datos del usuario o podría usar ensamblados que no se instalan de forma predeterminada con Visual Basic.  Puede extender el espacio de nombres `My` para incluir soluciones personalizadas a las tareas comunes que son específicas del entorno.  El espacio de nombres `My` se puede extender con facilidad para agregar nuevos miembros a fin de satisfacer las necesidades de crecimiento de la aplicación.  Además, las extensiones de espacio de nombres `My` se pueden distribuir a otros programadores como una plantilla de Visual Basic.  
  
###  <a name="addingtonamespace"></a> Agregar miembros al espacio de nombres My  
 Dado que `My` es un espacio de nombres como cualquier otro, puede agregarle propiedades de nivel superior con tan sólo agregar un módulo y especificar un `Namespace` de `My`.  Anote el módulo con el atributo `HideModuleName` como se muestra en el ejemplo siguiente.  El atributo `HideModuleName` garantiza que IntelliSense no mostrará el nombre del módulo cuando muestre los miembros del espacio de nombres `My`.  
  
 [!code-vb[VbVbcnExtendingMy#3](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_3.vb)]  
  
 Para agregar miembros al espacio de nombres `My`, agregue propiedades al módulo según sea necesario.  Para cada propiedad agregada al espacio de nombres `My`, agregue un campo privado de tipo `ThreadSafeObjectProvider(Of T)`, donde el tipo es el devuelto por la propiedad personalizada.  Este campo se usa para crear instancias del objeto seguras para subprocesos que se obtienen de la propiedad al llamar al método `GetInstance`.  Como resultado, cada subproceso que obtiene acceso a la propiedad extendida recibe su propia instancia del tipo devuelto.  En el ejemplo siguiente se agrega una propiedad denominada `SampleExtension` de tipo `SampleExtension` al espacio de nombres `My`:  
  
 [!code-vb[VbVbcnExtendingMy#4](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_4.vb)]  
  
##  <a name="addingevents"></a> Agregar eventos a objetos My personalizados  
 Puede usar el objeto `My.Application` para exponer eventos para los objetos `My` personalizados extendiendo la clase parcial `MyApplication` en el espacio de nombres `My`.  En los proyectos basados en Windows, puede hacer doble clic en el nodo **My Project** del proyecto en el **Explorador de soluciones**.  En el **Diseñador de proyectos** de Visual Basic, haga clic en la ficha `Application` y, a continuación, haga clic en el botón `View Application Events`.  Se crea un nuevo archivo denominado ApplicationEvents.vb.  Contiene el código siguiente para extender la clase `MyApplication`.  
  
 [!code-vb[VbVbcnExtendingMy#5](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_5.vb)]  
  
 Para agregar controladores de eventos para los objetos `My` personalizados, agréguelos a la clase `MyApplication`.  Los eventos personalizados permiten agregar código que se ejecutará al agregar o quitar un controlador de eventos o al provocar el evento.  Observe que el código `AddHandler` para un evento personalizado sólo se ejecuta si un usuario agrega el código para administrar el evento.  Por ejemplo, considere que el objeto `SampleExtension` de la sección anterior tiene un evento `Load` para el que desea agregar un controlador de eventos personalizado.  En el ejemplo de código siguiente se muestra un controlador de eventos personalizado denominado `SampleExtensionLoad` que se invocará cuando se produzca el evento `My.SampleExtension.Load`.  Cuando se agrega código para administrar el nuevo evento `My.SampleExtensionLoad`, se ejecuta la parte `AddHandler` de este código de evento personalizado.  El método `MyApplication_SampleExtensionLoad` se incluye en el ejemplo de código para mostrar un ejemplo de un controlador de eventos que administra el evento `My.SampleExtensionLoad`.  Observe que el evento `SampleExtensionLoad` estará disponible al seleccionar la opción **My Application Events** en la lista desplegable izquierda, situada sobre el editor de código al editar el archivo ApplicationEvents.vb.  
  
 [!code-vb[VbVbcnExtendingMy#6](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_6.vb)]  
  
##  <a name="design"></a> Instrucciones de diseño  
 Al desarrollar extensiones en el espacio de nombres `My`, use las instrucciones siguientes para ayudar a minimizar los costes de mantenimiento de sus componentes de extensión.  
  
-   **Incluya sólo la lógica de la extensión.** La lógica incluida en la extensión de espacio de nombres `My` debe incluir únicamente el código que se necesita para exponer la funcionalidad requerida en el espacio de nombres `My`.  Dado que su extensión residirá en proyectos de usuario como código fuente, actualizar el componente de extensión tendrá como resultado un mayor coste de mantenimiento, por lo que se debe evitar en la medida de lo posible.  
  
-   **Minimice las suposiciones en el proyecto.** Al crear las extensiones del espacio de nombres `My`, no dé por supuesto un conjunto de referencias, importaciones de nivel de proyecto o valores del compilador concretos \(por ejemplo, `Option Strict` desactivado\).  En su lugar, minimice las dependencias y califique por completo cualquier referencia de tipo mediante la palabra clave `Global`.  También, asegúrese de que la extensión se compila con `Option Strict` activado para minimizar los errores en la extensión.  
  
-   **Aísle el código de extensión.** Colocar el código en un archivo único facilita la implementación de la extensión como una plantilla de elementos de Visual Studio.  Para obtener más información, vea "Empaquetar e implementar extensiones" más adelante en este tema.  Colocar todo el código de la extensión de espacio de nombres `My` en un único archivo o una carpeta independiente de un proyecto también ayudará a los usuarios a buscar la extensión de espacio de nombres `My`.  
  
##  <a name="designing"></a> Diseñar bibliotecas de clases para My  
 Como ocurre con la mayoría de los modelos de objetos, algunos modelos de diseño funcionan bien con el espacio de nombres `My` y otros no.  Al diseñar una extensión en el espacio de nombres `My`, considere los principios siguientes:  
  
-   **Métodos sin estado.** Los métodos del espacio de nombres `My` deben proporcionar una solución completa a una tarea concreta.  Asegúrese de que los valores de parámetros que se pasan al método proporcionan toda la información necesaria para completar una tarea concreta.  Evite crear métodos que dependen del estado anterior, como conexiones abiertas a los recursos.  
  
-   **Instancias globales.** El único estado que se mantiene en el espacio de nombres `My` se aplica a todo el proyecto.  Por ejemplo, `My.Application.Info` encapsula un estado que se comparte en toda la aplicación.  
  
-   **Tipos de parámetros sencillos.** Mantenga los elementos sencillos y evite los tipos de parámetro complejos.  Es decir, cree métodos que no tomen entradas de parámetros o que tomen tipos de entradas sencillos, como cadenas, tipos primitivos, etc.  
  
-   **Métodos de generador.** Resulta inevitablemente difícil crear instancias de algunos tipos.  Proporcionar métodos de generador como extensiones al espacio de nombres `My` permite detectar y usar con mayor facilidad los tipos que pertenecen a esta categoría.  Un ejemplo de un método de generador que funciona bien es `My.Computer.FileSystem.OpenTextFileReader`.  Hay varios tipos de secuencia disponibles en .NET Framework.  Al especificar los archivos de texto de manera específica, `OpenTextFileReader` ayuda al usuario a comprender qué secuencia debe usar.  
  
 Estas instrucciones no descartan los principios de diseño generales para las bibliotecas de clases.  Más bien, son recomendaciones optimizadas para los programadores que usan Visual Basic y el espacio de nombres `My`.  Para consultar los principios de diseño generales de la creación de bibliotecas de clases, vea [Instrucciones de diseño de Framework](../Topic/Framework%20Design%20Guidelines.md).  
  
##  <a name="packaging"></a> Empaquetar e implementar extensiones  
 Puede incluir extensiones de espacio de nombres `My` en una plantilla de proyecto de Visual Studio o puede empaquetar sus extensiones e implementarlas como una plantilla de elementos de Visual Studio.  Al empaquetar las extensiones de espacio de nombres `My` como una plantilla de elementos de Visual Studio, puede aprovechar las funciones adicionales que proporciona Visual Basic.  Estas funciones permiten incluir una extensión cuando un proyecto hace referencia a un ensamblado determinado o permiten a los usuarios agregar explícitamente la extensión de espacio de nombres `My` usando la página **Extensiones My** del Diseñador de proyectos de Visual Basic.  
  
 Para obtener información detallada sobre cómo implementar extensiones de espacio de nombres `My`, vea [Empaquetar e implementar extensiones de My personalizadas](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md).  
  
## Vea también  
 [Empaquetar e implementar extensiones de My personalizadas](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)   
 [Ampliar el modelo de la aplicación de Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)   
 [Personalizar los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [Extensiones My \(página del Diseñador de proyectos\)](/visual-studio/ide/reference/my-extensions-page-project-designer-visual-basic)   
 [Aplicación \(Página, Diseñador de proyectos\) \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)   
 [Partial](../../../visual-basic/language-reference/modifiers/partial.md)
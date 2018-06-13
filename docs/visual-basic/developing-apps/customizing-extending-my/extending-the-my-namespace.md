---
title: Extender el espacio de nombres My en Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.AddingMyExtensions
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
ms.openlocfilehash: 22d9d0def302b870de6f3e5ca4c142758b21314c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591838"
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Extender el espacio de nombres My en Visual Basic
El `My` espacio de nombres en Visual Basic expone propiedades y métodos que permiten aprovechar fácilmente la eficacia de .NET Framework. El `My` simplifica el espacio de nombres de los problemas comunes de programación, a menudo reduce una tarea difícil en una sola línea de código. Además, el `My` espacio de nombres es totalmente extensible para que puedan personalizar el comportamiento de `My` y agregar nuevos servicios a su jerarquía para adaptarse a las necesidades específicas de aplicaciones. Este tema describe cómo personalizar los miembros existentes de la `My` espacio de nombres y cómo agregar sus propias clases personalizadas a la `My` espacio de nombres.  
  
 **Contenido del tema**  
  
-   [Personalizar existente a mi miembros Namespace](#customizing)  
  
-   [Agregar miembros a Mis objetos](#addingtoobjects)  
  
-   [Adición de objetos personalizados a la mi Namespace](#addingcustom)  
  
-   [Agregar miembros a la mi Namespace](#addingtonamespace)  
  
-   [Agregar eventos a objetos My personalizados](#addingevents)  
  
-   [Instrucciones de diseño](#design)  
  
-   [Diseño de bibliotecas de clases para My](#designing)  
  
-   [Empaquetar e implementar extensiones](#packaging)  
  
##  <a name="customizing"></a> Personalizar existente a mi miembros Namespace  
 El `My` con frecuencia utiliza el espacio de nombres de Visual Basic expone información acerca de la aplicación, el equipo y mucho más. Para obtener una lista completa de los objetos de la `My` espacio de nombres, vea [My Reference](../../../visual-basic/language-reference/keywords/my-reference.md). Puede que tenga que personalizar los miembros existentes de la `My` espacio de nombres para que mejor coincida con las necesidades de su aplicación. Cualquier propiedad de un objeto en el `My` espacio de nombres que no es de solo lectura se puede establecer en un valor personalizado.  
  
 Por ejemplo, supongamos que se usa con frecuencia el `My.User` objeto que se va a obtener acceso al contexto de seguridad actual para el usuario que ejecuta la aplicación. Sin embargo, su compañía utiliza un objeto de usuario personalizada para exponer información adicional y funciones para los usuarios dentro de la empresa. En este escenario, puede reemplazar el valor predeterminado de la `My.User.CurrentPrincipal` propiedad con una instancia de su propio objeto de entidad de seguridad personalizado, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbcnExtendingMy#1](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_1.vb)]  
  
 Establecer el `CurrentPrincipal` propiedad en la `My.User` objeto cambia la identidad bajo la que se ejecuta la aplicación. La `My.User` objeto, a su vez, devuelve información sobre el usuario recién especificado.  
  
##  <a name="addingtoobjects"></a> Agregar miembros a Mis objetos  
 Los tipos devueltos desde `My.Application` y `My.Computer` se definen como `Partial` clases. Por lo tanto, puede ampliar el `My.Application` y `My.Computer` objetos mediante la creación de un `Partial` clase denominada `MyApplication` o `MyComputer`. La clase no puede ser un `Private` clase. Si se especifica la clase como parte de la `My` espacio de nombres, puede agregar propiedades y métodos que se van a incluidos con la `My.Application` o `My.Computer` objetos.  
  
 Por ejemplo, en el ejemplo siguiente se agrega una propiedad denominada `DnsServerIPAddresses` a la `My.Computer` objeto.  
  
 [!code-vb[VbVbcnExtendingMy#2](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_2.vb)]  
  
##  <a name="addingcustom"></a> Adición de objetos personalizados a la mi Namespace  
 Aunque la `My` espacio de nombres proporciona soluciones para muchas tareas de programación comunes, puede encontrar las tareas que el `My` no se ocupa del espacio de nombres. Por ejemplo, la aplicación puede tener acceso a los servicios de directorio personalizados para los datos de usuario o la aplicación podría utilizar ensamblados que no se instalan de forma predeterminada con Visual Basic. Puede ampliar el `My` espacio de nombres para incluir soluciones personalizadas a las tareas comunes que son específicas de su entorno. El `My` espacio de nombres se puede ampliar fácilmente para agregar nuevos miembros para satisfacer las necesidades crecientes de aplicación. Además, puede implementar su `My` extensiones de espacio de nombres a otros desarrolladores como una plantilla de Visual Basic.  
  
###  <a name="addingtonamespace"></a> Agregar miembros a la mi Namespace  
 Dado que `My` es un espacio de nombres como cualquier otro espacio de nombres, puede agregar propiedades de nivel superior a él, sólo debe agregar un módulo y especificar un `Namespace` de `My`. Anote el módulo con el `HideModuleName` atributo tal como se muestra en el ejemplo siguiente. El `HideModuleName` atributo garantiza que IntelliSense no mostrará el nombre del módulo al que muestra los miembros de la `My` espacio de nombres.  
  
 [!code-vb[VbVbcnExtendingMy#3](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_3.vb)]  
  
 Para agregar miembros a la `My` espacio de nombres, agregue propiedades según sea necesario para el módulo. Para cada propiedad agregada a la `My` espacio de nombres, agregue un campo privado del tipo `ThreadSafeObjectProvider(Of T)`, donde el tipo es el tipo devuelto por la propiedad personalizada. Este campo se usa para crear instancias de objetos de subprocesos que va a devolver la propiedad mediante una llamada a la `GetInstance` método. Como resultado, cada subproceso que tiene acceso a la propiedad extendida recibe su propia instancia del tipo devuelto. En el ejemplo siguiente se agrega una propiedad denominada `SampleExtension` que es de tipo `SampleExtension` a la `My` espacio de nombres:  
  
 [!code-vb[VbVbcnExtendingMy#4](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_4.vb)]  
  
##  <a name="addingevents"></a> Agregar eventos a objetos My personalizados  
 Puede usar el `My.Application` objeto que se va a exponer eventos para su personalizado `My` objetos extendiendo la `MyApplication` clase parcial en la `My` espacio de nombres. Para los proyectos basados en Windows, puede hacer doble clic el **mi proyecto** nodo para el proyecto en **el Explorador de soluciones**. En Visual Basic **Diseñador de proyectos**, haga clic en el `Application` ficha y, a continuación, haga clic en el `View Application Events` botón. Se creará un nuevo archivo que se denomina ApplicationEvents.vb. Contiene el siguiente código para extender la `MyApplication` clase.  
  
 [!code-vb[VbVbcnExtendingMy#5](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_5.vb)]  
  
 Puede agregar controladores de eventos para su personalizado `My` objetos mediante la adición de controladores de eventos personalizados para el `MyApplication` clase. Eventos personalizados permiten agregar código que se ejecutará cuando se agrega un controlador de eventos, quitar, o se genera el evento. Tenga en cuenta que el `AddHandler` de código para un evento personalizado se ejecuta sólo si el código se agrega un usuario para controlar el evento. Por ejemplo, considere la posibilidad de que el `SampleExtension` objeto de la sección anterior tiene un `Load` eventos que desea agregar un controlador de eventos personalizado para. En el ejemplo de código siguiente se muestra un controlador de eventos personalizado denominado `SampleExtensionLoad` será la que se invoca cuando el `My.SampleExtension.Load` se produce el evento. Cuando se agrega código para controlar el nuevo `My.SampleExtensionLoad` eventos, el `AddHandler` parte de este código de evento personalizado se ejecuta. El `MyApplication_SampleExtensionLoad` método se incluye en el ejemplo de código se muestra un ejemplo de un controlador de eventos que controla el `My.SampleExtensionLoad` eventos. Tenga en cuenta que la `SampleExtensionLoad` evento estará disponible cuando se selecciona el **My Application Events** opción en la lista desplegable izquierda sobre el Editor de código cuando se edita el archivo ApplicationEvents.vb.  
  
 [!code-vb[VbVbcnExtendingMy#6](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_6.vb)]  
  
##  <a name="design"></a> Instrucciones de diseño  
 Al desarrollar extensiones para el `My` espacio de nombres, utilice las instrucciones siguientes para ayudar a reducir los costos de mantenimiento de los componentes de extensión.  
  
-   **Incluir la lógica de la extensión.** La lógica que se incluyen en el `My` extensión de espacio de nombres debe incluir solo el código que se necesita para exponer la funcionalidad necesaria en el `My` espacio de nombres. Dado que la extensión residen en proyectos de usuario como código fuente, actualizar el componente de extensión conlleva un mayor coste de mantenimiento y debería evitarse si es posible.  
  
-   **Minimizar las suposiciones de proyecto.** Al crear las extensiones de la `My` espacio de nombres, no se da por supuesto un conjunto de referencias, las importaciones de nivel de proyecto o valores del compilador concretos (por ejemplo, `Option Strict` off). En su lugar, minimizar las dependencias y calificar completamente todas las referencias de tipo mediante el `Global` palabra clave. Además, asegúrese de que la extensión se compila con `Option Strict` de minimizar los errores en la extensión.  
  
-   **Aislar el código de extensión.** Coloque el código en un único archivo hace que la extensión puede implementar fácilmente como una plantilla de elemento de Visual Studio. Para obtener más información, vea "Empaquetar e implementar extensiones" más adelante en este tema. Colocar todos los `My` código de la extensión de espacio de nombres en un único archivo o una carpeta independiente en un proyecto también ayudará a los usuarios buscar el `My` extensión de espacio de nombres.  
  
##  <a name="designing"></a> Diseño de bibliotecas de clases para My  
 Como sucede con la mayoría de los modelos de objetos, algunos modelos de diseño funcionan bien en el `My` espacio de nombres y otros no. Al diseñar una extensión a la `My` espacio de nombres, tenga en cuenta los siguientes principios:  
  
-   **Métodos sin estado.** Métodos en el `My` espacio de nombres debe proporcionar una solución completa para una tarea específica. Asegúrese de que los valores de parámetro que se pasan al método proporcionan toda la información necesaria para completar la tarea determinada. Evite crear métodos que se basan en el estado anterior, como conexiones abiertas a los recursos.  
  
-   **Instancias globales.** El único estado que se mantiene en el `My` espacio de nombres es global para el proyecto. Por ejemplo, `My.Application.Info` encapsula un estado que se comparte en toda la aplicación.  
  
-   **Tipos de parámetro simples.** No complicar las cosas, evite los tipos de parámetros complejos. En su lugar, crear métodos que no tomen ningún parámetro de entrada o que tomen tipos de entrada simples como cadenas, tipos primitivos y así sucesivamente.  
  
-   **Métodos de generador.** Algunos tipos tienen necesariamente difíciles de crear una instancia. Proporciona métodos de generador como extensiones a la `My` espacio de nombres permite detectar más fácilmente y usen tipos que pertenecen a esta categoría. Un ejemplo de un método de generador que funciona bien es `My.Computer.FileSystem.OpenTextFileReader`. Hay varios tipos de secuencia disponibles en .NET Framework. Mediante la especificación de archivos de texto en concreto, la `OpenTextFileReader` ayuda al usuario a comprender qué secuencia debe usar.  
  
 Estas instrucciones no descartan los principios de diseño generales para las bibliotecas de clases. En su lugar, son recomendaciones que se optimizan para desarrolladores que usan Visual Basic y `My` espacio de nombres. Para los principios de diseño generales para la creación de bibliotecas de clases, consulte [directrices de diseño de Framework](../../../standard/design-guidelines/index.md).  
  
##  <a name="packaging"></a> Empaquetar e implementar extensiones  
 Puede incluir `My` extensiones de espacio de nombres en una plantilla de proyecto de Visual Studio, o pueden empaquetar sus extensiones e implementarlas como una plantilla de elemento de Visual Studio. Al empaquetar la `My` extensiones de espacio de nombres como una plantilla de elemento de Visual Studio, se puede aprovechar capacidades adicionales proporcionadas por Visual Basic. Estas funciones le permiten incluir una extensión cuando un proyecto hace referencia a un ensamblado determinado o permiten a los usuarios agregar explícitamente la `My` extensión de espacio de nombres mediante el uso de la **extensiones My** página de Visual Basic Diseñador de proyectos.  
  
 Para obtener más información sobre cómo implementar `My` extensiones de espacio de nombres, vea [empaquetado e implementación Custom My Extensions](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md).  
  
## <a name="see-also"></a>Vea también  
 [Empaquetado e implementación de extensiones de My personalizadas](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)  
 [Extensión del modelo de la aplicación de Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)  
 [Personalización de los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 [Mi página de extensiones, Diseñador de proyectos](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)  
 [Página de aplicación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [Partial](../../../visual-basic/language-reference/modifiers/partial.md)

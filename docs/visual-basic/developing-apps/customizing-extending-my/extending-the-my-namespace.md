---
title: Extender el My Namespace en Visual Basic | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AddingMyExtensions
dev_langs:
- VB
helpviewer_keywords:
- My namespace, customizing
- My namespace
- My namespace, extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1d1e957536f35b81a9672994c9d4d261afb764ea
ms.lasthandoff: 03/13/2017

---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Extender el espacio de nombres My en Visual Basic
El `My` espacio de nombres en Visual Basic expone propiedades y métodos que le permiten aprovechar fácilmente la eficacia de .NET Framework. El `My` espacio de nombres simplifica los problemas de programación comunes, a menudo reduce una tarea difícil a una sola línea de código. Además, el `My` espacio de nombres es completamente extensible que puede personalizar el comportamiento de `My` y agregar nuevos servicios a su jerarquía para adaptarse a las necesidades específicas de aplicaciones. En este tema se describe tanto cómo personalizar los miembros existentes de la `My` espacio de nombres y cómo agregar sus propias clases personalizadas para el `My` espacio de nombres.  
  
 **Contenido del tema**  
  
-   [Personalizar existente de los miembros de mi Namespace](#customizing)  
  
-   [Agregar miembros a Mis objetos](#addingtoobjects)  
  
-   [Agregar objetos personalizados en el My Namespace](#addingcustom)  
  
-   [Agregar miembros a la My Namespace](#addingtonamespace)  
  
-   [Agregar eventos a objetos My personalizados](#addingevents)  
  
-   [Instrucciones de diseño](#design)  
  
-   [Diseño de bibliotecas de clases para My](#designing)  
  
-   [Empaquetar e implementar extensiones](#packaging)  
  
##  <a name="customizing"></a>Personalizar existente de los miembros de mi Namespace  
 El `My` con frecuencia utiliza el espacio de nombres de Visual Basic expone información acerca de la aplicación, el equipo y mucho más. Para obtener una lista completa de los objetos de la `My` espacio de nombres, vea [My Reference](../../../visual-basic/language-reference/keywords/my-reference.md). Es posible que deba personalizar los miembros existentes de la `My` espacio de nombres para que mejor satisfagan las necesidades de su aplicación. Cualquier propiedad de un objeto en el `My` espacio de nombres que no es de sólo lectura puede establecerse en un valor personalizado.  
  
 Por ejemplo, suponga que usa con frecuencia el `My.User` objeto para tener acceso al contexto de seguridad actual para el usuario que ejecuta la aplicación. Sin embargo, su compañía usa un objeto de usuario personalizada para exponer información adicional y funciones para los usuarios dentro de la empresa. En este escenario, puede reemplazar el valor predeterminado de la `My.User.CurrentPrincipal` propiedad con una instancia de su propio objeto principal personalizado, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[1 VbVbcnExtendingMy](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_1.vb)]  
  
 Establecer el `CurrentPrincipal` propiedad en la `My.User` objeto cambia la identidad bajo la que se ejecuta la aplicación. La `My.User` objeto, a su vez, devuelve información sobre el usuario recién especificado.  
  
##  <a name="addingtoobjects"></a>Agregar miembros a Mis objetos  
 Los tipos devueltos desde `My.Application` y `My.Computer` se definen como `Partial` clases. Por lo tanto, puede ampliar el `My.Application` y `My.Computer` objetos mediante la creación de un `Partial` clase denominada `MyApplication` o `MyComputer`. La clase no puede ser un `Private` clase. Si se especifica la clase como parte de la `My` espacio de nombres, puede agregar propiedades y métodos que se incluirán con el `My.Application` o `My.Computer` objetos.  
  
 Por ejemplo, en el ejemplo siguiente se agrega una propiedad denominada `DnsServerIPAddresses` a la `My.Computer` objeto.  
  
 [!code-vb[VbVbcnExtendingMy&#2;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_2.vb)]  
  
##  <a name="addingcustom"></a>Agregar objetos personalizados en el My Namespace  
 Aunque la `My` espacio de nombres proporciona soluciones para muchas tareas de programación comunes, puede encontrar tareas que el `My` no resuelve el espacio de nombres. Por ejemplo, la aplicación puede tener acceso a los servicios de directorio personalizado para datos de usuario o la aplicación podría usar ensamblados que no se instalan de forma predeterminada con Visual Basic. Puede ampliar el `My` incluyen soluciones personalizadas para tareas comunes que son específicas de su entorno de espacio de nombres. El `My` espacio de nombres se puede ampliar fácilmente para agregar nuevos miembros para satisfacer las necesidades crecientes de aplicación. Además, puede implementar su `My` extensiones de espacio de nombres a otros desarrolladores como una plantilla de Visual Basic.  
  
###  <a name="addingtonamespace"></a>Agregar miembros a la My Namespace  
 Porque `My` es un espacio de nombres como cualquier otro espacio de nombres, puede agregar propiedades de nivel superior a él simplemente agregando un módulo y especificando un `Namespace` de `My`. Anote el módulo con el `HideModuleName` atributo tal como se muestra en el ejemplo siguiente. El `HideModuleName` atributo garantiza que IntelliSense no mostrará el nombre del módulo cuando muestre los miembros de la `My` espacio de nombres.  
  
 [!code-vb[VbVbcnExtendingMy&3;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_3.vb)]  
  
 Agregar miembros a la `My` espacio de nombres, agregue propiedades según sea necesario para el módulo. Para cada propiedad agregada a la `My` espacio de nombres, agregue un campo privado de tipo `ThreadSafeObjectProvider(Of T)`, donde el tipo es el tipo devuelto por la propiedad personalizada. Este campo se usa para crear instancias de objetos de subprocesos que será devuelto por la propiedad llamando a la `GetInstance` (método). Como resultado, cada subproceso que tiene acceso a la propiedad extendida recibe su propia instancia del tipo devuelto. En el ejemplo siguiente se agrega una propiedad denominada `SampleExtension` que es de tipo `SampleExtension` a la `My` espacio de nombres:  
  
 [!code-vb[VbVbcnExtendingMy Nº&4;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_4.vb)]  
  
##  <a name="addingevents"></a>Agregar eventos a objetos My personalizados  
 Puede usar el `My.Application` objeto exponer eventos para personalizado `My` objetos extendiendo la `MyApplication` clase parcial en la `My` espacio de nombres. Para los proyectos basados en Windows, hacer doble clic en el **mi proyecto** nodo de proyecto en el **el Explorador de soluciones**. En Visual Basic **Project Designer**, haga clic en el `Application` y, a continuación, haga clic en el `View Application Events` botón. Se creará un nuevo archivo denominado ApplicationEvents.vb. Contiene el siguiente código para extender el `MyApplication` clase.  
  
 [!code-vb[VbVbcnExtendingMy&#5;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_5.vb)]  
  
 Puede agregar controladores de eventos para su personalizado `My` objetos mediante la adición de controladores de eventos personalizados para el `MyApplication` clase. Eventos personalizados permiten agregar código que se ejecutará cuando un controlador de eventos se agrega, quita o se genera el evento. Tenga en cuenta que el `AddHandler` de código para un evento personalizado que se ejecuta sólo si el código se agrega un usuario para controlar el evento. Por ejemplo, considere la posibilidad de que el `SampleExtension` objeto de la sección anterior tiene un `Load` eventos que desea agregar un controlador de eventos personalizado. En el ejemplo de código siguiente se muestra un controlador de eventos personalizado denominado `SampleExtensionLoad` que será invocado cuando la `My.SampleExtension.Load` se produce el evento. Cuando se agrega código para controlar la nueva `My.SampleExtensionLoad` evento, el `AddHandler` se ejecuta la parte de este código de evento personalizado. El `MyApplication_SampleExtensionLoad` método está incluido en el ejemplo de código se muestra un ejemplo de un controlador de eventos que controla el `My.SampleExtensionLoad` eventos. Tenga en cuenta que el `SampleExtensionLoad` eventos estará disponible cuando se selecciona el **Mis eventos de aplicación** opción en la lista desplegable izquierda sobre el Editor de código cuando se edita el archivo ApplicationEvents.vb.  
  
 [!code-vb[VbVbcnExtendingMy&6;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_6.vb)]  
  
##  <a name="design"></a>Instrucciones de diseño  
 Al desarrollar extensiones a la `My` espacio de nombres, utilice las instrucciones siguientes para ayudar a reducir los costos de mantenimiento de los componentes de extensión.  
  
-   **Incluir la lógica de la extensión.** La lógica que se incluye en el `My` extensión del espacio de nombres debe incluir sólo el código que se necesita para exponer la funcionalidad requerida en el `My` espacio de nombres. Dado que su extensión residirá en proyectos de usuario como código fuente, actualizar el componente de extensión incurre en un costo de mantenimiento alto y debe evitarse si es posible.  
  
-   **Minimizar los supuestos del proyecto.** Al crear las extensiones de la `My` espacio de nombres, no suponga un conjunto de referencias, importaciones de nivel de proyecto o valores del compilador concretos (por ejemplo, `Option Strict` off). En su lugar, minimizar las dependencias y calificar completamente todas las referencias de tipo mediante el `Global` (palabra clave). Además, asegúrese de que la extensión se compila con `Option Strict` activado a minimizar los errores en la extensión.  
  
-   **Aislar el código de extensión.** Coloque el código en un solo archivo hace que la extensión puede implementar fácilmente como una plantilla de elemento de Visual Studio. Para obtener más información, vea "Empaquetar e implementar extensiones" más adelante en este tema. Colocar todos los `My` código de extensión del espacio de nombres en un único archivo o una carpeta en un proyecto independiente también ayuda a los usuarios encontrar la `My` extensión del espacio de nombres.  
  
##  <a name="designing"></a>Diseño de bibliotecas de clases para My  
 Como sucede con la mayoría de los modelos de objetos, algunos modelos de diseño funcionan bien en el `My` espacio de nombres y otras no. Al diseñar una extensión de la `My` espacio de nombres, tenga en cuenta los siguientes principios:  
  
-   **Métodos sin estado.** Métodos en el `My` espacio de nombres debe proporcionar una solución completa a una tarea específica. Asegúrese de que los valores de parámetro que se pasan al método proporcionan toda la información necesaria para completar una tarea concreta. Evite crear métodos que dependen del estado anterior, como conexiones abiertas a los recursos.  
  
-   **Instancias globales.** El único estado que se mantiene en el `My` espacio de nombres es global para el proyecto. Por ejemplo, `My.Application.Info` encapsula un estado que se comparte en toda la aplicación.  
  
-   **Tipos de parámetro simples.** Simplificar las cosas, evite los tipos de parámetros complejos. En su lugar, cree métodos que no tomen ningún parámetro de entrada o que tomen tipos de entradas sencillos, como cadenas, tipos primitivos y así sucesivamente.  
  
-   **Métodos de generador.** Algunos tipos tienen necesariamente difíciles crear instancias. Proporcionar métodos de generador como extensiones a la `My` espacio de nombres permite detectar más fácilmente y utilizar tipos que pertenecen a esta categoría. Un ejemplo de un método de generador que funciona bien es `My.Computer.FileSystem.OpenTextFileReader`. Hay varios tipos de secuencia disponibles en .NET Framework. Especificar archivos de texto en concreto, el `OpenTextFileReader` ayuda al usuario a comprender qué secuencia debe usar.  
  
 Estas instrucciones no descartan los principios de diseño generales para las bibliotecas de clases. En su lugar, son recomendaciones optimizadas para los desarrolladores que utilizan Visual Basic y `My` espacio de nombres. Para principios de diseño generales para crear bibliotecas de clases, consulte [las directrices de diseño de Framework](http://msdn.microsoft.com/library/5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b).  
  
##  <a name="packaging"></a>Empaquetar e implementar extensiones  
 Puede incluir `My` extensiones de espacio de nombres en una plantilla de proyecto de Visual Studio o pueden empaquetar sus extensiones e implementarlas como una plantilla de elemento de Visual Studio. Al empaquetar su `My` extensiones de espacio de nombres como una plantilla de elemento de Visual Studio, se puede aprovechar capacidades adicionales de Visual Basic. Estas capacidades permiten incluir una extensión cuando un proyecto hace referencia a un ensamblado determinado o permiten a los usuarios agregar explícitamente la `My` extensión del espacio de nombres utilizando la **extensiones My** página del Diseñador de proyectos de Visual Basic.  
  
 Para obtener más información sobre cómo implementar `My` extensiones de espacio de nombres, vea [empaquetado e implementación Custom My Extensions](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md).  
  
## <a name="see-also"></a>Vea también  
 [Empaquetar e implementar extensiones de My personalizadas](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)   
 [Ampliar el modelo de aplicación de Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)   
 [Personalizar los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [Mi página de extensiones, Diseñador de proyectos](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)   
 [Página de aplicación, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)   
 [Partial](../../../visual-basic/language-reference/modifiers/partial.md)

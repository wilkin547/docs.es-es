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
ms.openlocfilehash: 4d7bb6eef398746a4bd2dc4dbf3d526da1c1e0f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814167"
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Extender el espacio de nombres My en Visual Basic
El `My` espacio de nombres en Visual Basic expone propiedades y métodos que permiten aprovechar fácilmente la eficacia de .NET Framework. El `My` simplifica el espacio de nombres de los problemas de programación comunes, a menudo reduce una tarea difícil en una sola línea de código. Además, el `My` espacio de nombres es totalmente extensible para que puedan personalizar el comportamiento de `My` y agregar nuevos servicios a su jerarquía para adaptarse a necesidades específicas de aplicaciones. En este tema se describe cómo personalizar los miembros existentes de la `My` espacio de nombres y cómo agregar sus propias clases personalizadas para el `My` espacio de nombres.  
  
 **Contenido del tema**  
  
-   [Personalizar los existentes a los miembros de mi Namespace](#customizing)  
  
-   [Agregar miembros a Mis objetos](#addingtoobjects)  
  
-   [Adición de objetos personalizados a la mi Namespace](#addingcustom)  
  
-   [Agregar miembros a la mi Namespace](#addingtonamespace)  
  
-   [Agregar eventos a Mis objetos personalizados](#addingevents)  
  
-   [Instrucciones de diseño](#design)  
  
-   [Diseño de bibliotecas de clases para mi](#designing)  
  
-   [Empaquetar e implementar extensiones](#packaging)  
  
## <a name="customizing"></a> Personalizar los existentes a los miembros de mi Namespace  
 El `My` espacio de nombres en Visual Basic expone información acerca de la aplicación, el equipo y mucho más usada con frecuencia. Para obtener una lista completa de los objetos de la `My` espacio de nombres, vea [My Reference](../../../visual-basic/language-reference/keywords/my-reference.md). Puede que tenga que personalizar los miembros existentes de la `My` espacio de nombres para que el mejor coincide con las necesidades de su aplicación. Cualquier propiedad de un objeto en el `My` espacio de nombres que no es de solo lectura se puede establecer en un valor personalizado.  
  
 Por ejemplo, supongamos que se usa con frecuencia el `My.User` objeto para tener acceso al contexto de seguridad actual para el usuario que ejecuta la aplicación. Sin embargo, su empresa usa un objeto de usuario personalizada para exponer información adicional y capacidades para los usuarios dentro de la empresa. En este escenario, puede reemplazar el valor predeterminado de la `My.User.CurrentPrincipal` propiedad con una instancia de su propio objeto de entidad de seguridad personalizado, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbcnExtendingMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#1)]  
  
 Establecer el `CurrentPrincipal` propiedad en el `My.User` objeto cambia la identidad que se ejecuta la aplicación. La `My.User` objeto, a su vez, devuelve información sobre el usuario recién especificado.  
  
## <a name="addingtoobjects"></a> Agregar miembros a Mis objetos  
 Los tipos devueltos desde `My.Application` y `My.Computer` se definen como `Partial` clases. Por lo tanto, puede ampliar el `My.Application` y `My.Computer` objetos mediante la creación de un `Partial` clase denominada `MyApplication` o `MyComputer`. La clase no puede ser un `Private` clase. Si especifica la clase como parte de la `My` espacio de nombres, puede agregar propiedades y métodos que se incluirá con la `My.Application` o `My.Computer` objetos.  
  
 Por ejemplo, en el ejemplo siguiente se agrega una propiedad denominada `DnsServerIPAddresses` a la `My.Computer` objeto.  
  
 [!code-vb[VbVbcnExtendingMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class2.vb#2)]  
  
## <a name="addingcustom"></a> Adición de objetos personalizados a la mi Namespace  
 Aunque el `My` espacio de nombres proporciona soluciones para muchas tareas comunes de programación, puede encontrar las tareas que el `My` no resuelve el espacio de nombres. Por ejemplo, la aplicación puede tener acceso a los servicios de directorio personalizado para los datos de usuario o la aplicación podría utilizar los ensamblados que no se instalan de forma predeterminada con Visual Basic. Puede ampliar el `My` espacio de nombres para incluir soluciones personalizadas para las tareas comunes que son específicas de su entorno. El `My` espacio de nombres se puede ampliar fácilmente para agregar nuevos miembros para satisfacer las crecientes necesidades de la aplicación. Además, puede implementar su `My` extensiones de espacio de nombres a otros desarrolladores como una plantilla de Visual Basic.  
  
### <a name="addingtonamespace"></a> Agregar miembros a la mi Namespace  
 Dado que `My` es un espacio de nombres como cualquier otro espacio de nombres, puede agregar propiedades de nivel superior a él simplemente agregando un módulo y especificando un `Namespace` de `My`. Anote el módulo con el `HideModuleName` atributo tal como se muestra en el ejemplo siguiente. El `HideModuleName` atributo asegura que IntelliSense no mostrará el nombre del módulo al que muestra los miembros de la `My` espacio de nombres.  
  
 [!code-vb[VbVbcnExtendingMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#3)]  
  
 Para agregar miembros a la `My` espacio de nombres, agregue las propiedades según sea necesario para el módulo. Para cada propiedad que se agrega a la `My` espacio de nombres, agregue un campo privado de tipo `ThreadSafeObjectProvider(Of T)`, donde el tipo es el tipo devuelto por la propiedad personalizada. Este campo se usa para crear instancias de objetos de subprocesos que será devuelto por la propiedad mediante una llamada a la `GetInstance` método. Como resultado, cada subproceso que tiene acceso a la propiedad extendida recibe su propia instancia del tipo devuelto. En el ejemplo siguiente se agrega una propiedad denominada `SampleExtension` que es de tipo `SampleExtension` a la `My` espacio de nombres:  
  
 [!code-vb[VbVbcnExtendingMy#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#4)]  
  
## <a name="addingevents"></a> Agregar eventos a Mis objetos personalizados  
 Puede usar el `My.Application` objeto exponer eventos para personalizado `My` objetos extendiendo el `MyApplication` clase parcial en la `My` espacio de nombres. Para los proyectos basados en Windows, hacer doble clic en el **mi proyecto** nodo para el proyecto en **el Explorador de soluciones**. En Visual Basic **Diseñador de proyectos**, haga clic en el `Application` pestaña y, a continuación, haga clic en el `View Application Events` botón. Se creará un nuevo archivo denominado ApplicationEvents.vb. Contiene el siguiente código para extender el `MyApplication` clase.  
  
 [!code-vb[VbVbcnExtendingMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#5)]  
  
 Puede agregar controladores de eventos para el personalizado `My` objetos mediante la adición de controladores de eventos personalizados a la `MyApplication` clase. Eventos personalizados permiten agregar código que se ejecutará cuando se agrega un controlador de eventos, quitar, o se genera el evento. Tenga en cuenta que el `AddHandler` de código para un evento personalizado se ejecuta sólo si el código se agrega un usuario para controlar el evento. Por ejemplo, considere la posibilidad de que el `SampleExtension` objeto desde la sección anterior tiene un `Load` eventos que desea agregar un controlador de eventos personalizado. En el ejemplo de código siguiente se muestra un controlador de eventos personalizado denominado `SampleExtensionLoad` será la que se invoca cuando el `My.SampleExtension.Load` se produce el evento. Cuando se agrega código para controlar el nuevo `My.SampleExtensionLoad` eventos, el `AddHandler` parte de este código de evento personalizado se ejecuta. El `MyApplication_SampleExtensionLoad` método se incluye en el ejemplo de código para mostrar un ejemplo de un controlador de eventos que controla la `My.SampleExtensionLoad` eventos. Tenga en cuenta que el `SampleExtensionLoad` eventos estará disponible cuando se selecciona el **Mis eventos de aplicación** opción en la lista desplegable izquierda por encima del Editor de código cuando se edita el archivo ApplicationEvents.vb.  
  
 [!code-vb[VbVbcnExtendingMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#6)]  
  
## <a name="design"></a> Instrucciones de diseño  
 Al desarrollar extensiones para la `My` espacio de nombres, utilice las siguientes directrices para ayudar a reducir los costos de mantenimiento de los componentes de extensión.  
  
-   **Incluir la lógica de la extensión.** La lógica que se incluye en el `My` extensión del espacio de nombres debe incluir únicamente el código que se necesita para exponer la funcionalidad requerida en el `My` espacio de nombres. Dado que la extensión residen en los proyectos de usuario como código fuente, actualizar el componente de extensión incurre en un costo de mantenimiento alto y debería evitarse si es posible.  
  
-   **Minimizar las suposiciones de proyecto.** Cuando cree sus extensiones de la `My` espacio de nombres, no suponga un conjunto de referencias, las importaciones de nivel de proyecto o configuración de compilador específica (por ejemplo, `Option Strict` off). En su lugar, minimizar las dependencias y calificar todas las referencias de tipo mediante el uso de la `Global` palabra clave. Además, asegúrese de que se compila con la extensión `Option Strict` activado a minimizar los errores en la extensión.  
  
-   **Aislar el código de extensión.** Coloque el código en un único archivo hace que la extensión que pueden implementar fácilmente como una plantilla de elemento de Visual Studio. Para obtener más información, vea "Empaquetar e implementar extensiones" más adelante en este tema. Colocar todas la `My` código de extensión de espacio de nombres en un único archivo o una carpeta independiente en un proyecto también ayuda a los usuarios encontrar la `My` extensión del espacio de nombres.  
  
## <a name="designing"></a> Diseño de bibliotecas de clases para mi  
 Como sucede con la mayoría de los modelos de objetos, algunos patrones de diseño funcionan bien en el `My` espacio de nombres y otras no. Al diseñar una extensión de la `My` espacio de nombres, tenga en cuenta los siguientes principios:  
  
-   **Métodos sin estado.** Los métodos en el `My` espacio de nombres debe proporcionar una solución completa a una tarea específica. Asegúrese de que los valores de parámetro que se pasan al método proporcionan toda la información necesaria para completar la tarea concreta. Evite crear métodos que se basan en un estado anterior, por ejemplo, las conexiones abiertas a los recursos.  
  
-   **Instancias globales.** El único estado que se mantiene en el `My` espacio de nombres es global para el proyecto. Por ejemplo, `My.Application.Info` encapsula el estado que se comparte en toda la aplicación.  
  
-   **Tipos de parámetro simples.** Simplificar las cosas, ya que evita los tipos de parámetros complejos. En su lugar, cree los métodos que no tomar ningún parámetro de entrada o que tomen tipos simples de entrada como cadenas, tipos primitivos y así sucesivamente.  
  
-   **Métodos de generador.** Algunos tipos tienen necesariamente es difíciles crear instancias. Proporcionar métodos de generador como extensiones a la `My` espacio de nombres permite detectar más fácilmente y utilizar tipos que pertenecen a esta categoría. Es un ejemplo de un método de generador que funciona bien `My.Computer.FileSystem.OpenTextFileReader`. Hay varios tipos de secuencia de .NET Framework. Mediante la especificación de archivos de texto en concreto, el `OpenTextFileReader` ayuda al usuario a entender qué flujo se va a usar.  
  
 Estas instrucciones no excluye los principios de diseño generales para las bibliotecas de clases. En su lugar, son las recomendaciones que se optimizan para desarrolladores que usan Visual Basic y `My` espacio de nombres. Para los principios de diseño generales para la creación de bibliotecas de clases, vea [instrucciones de diseño de Framework](../../../standard/design-guidelines/index.md).  
  
## <a name="packaging"></a> Empaquetar e implementar extensiones  
 Puede incluir `My` extensiones de espacio de nombres en una plantilla de proyecto de Visual Studio, o pueden empaquetar sus extensiones e implementarlas como una plantilla de elemento de Visual Studio. Al empaquetar la `My` extensiones de espacio de nombres como una plantilla de elemento de Visual Studio, puede sacar partido de las capacidades adicionales proporcionadas por Visual Basic. Estas capacidades permiten incluir una extensión cuando un proyecto hace referencia a un ensamblado determinado o permitir que los usuarios agregar explícitamente la `My` extensión del espacio de nombres mediante el **extensiones My** página de Visual Basic Diseñador de proyectos.  
  
 Para obtener más información sobre cómo implementar `My` las extensiones de espacio de nombres, vea [empaquetado e implementación de Custom My Extensions](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md).  
  
## <a name="see-also"></a>Vea también

- [Empaquetado e implementación de extensiones de My personalizadas](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)
- [Extensión del modelo de la aplicación de Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [Personalización de los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Página Mis extensiones del Diseñador de proyectos](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
- [Página de aplicación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Partial](../../../visual-basic/language-reference/modifiers/partial.md)

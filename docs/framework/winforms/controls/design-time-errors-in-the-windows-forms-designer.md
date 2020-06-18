---
title: Errores en tiempo de diseño en el Diseñador de Windows Forms
titleSuffix: ''
description: Obtenga información sobre los errores que se producen cuando no se puede cargar el Diseñador de Windows Forms debido a un error en el código, en un componente de terceros o en otro lugar.
ms.date: 09/09/2019
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d9c3993dfce9312c3271c499b6c0cd0c11253ca8
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904395"
---
# <a name="windows-forms-designer-error-page"></a>Diseñador de Windows Forms página de error

Si el Diseñador de Windows Forms no se puede cargar debido a un error en el código, en un componente de terceros o en otro lugar, verá una página de error en lugar del diseñador. Esta página de error no implica necesariamente un error en el diseñador. El error puede estar en alguna parte de la página de código subyacente denominada \<your-form-name> . Designer.cs. Los errores aparecen en barras amarillas contraíble con un vínculo para saltar a la ubicación del error en la página de códigos.

![Diseñador de Windows Forms página de error](media/windows-forms-designer-error-page-collapsed.png)

Puede optar por omitir los errores y continuar cargando el diseñador haciendo clic en **omitir y continuar**. Esta acción puede producir un comportamiento inesperado; por ejemplo, puede que los controles no aparezcan en la superficie de diseño.

## <a name="instances-of-this-error"></a>Instancias de este error

Cuando se expande la barra de error amarilla, se muestra cada instancia del error. Muchos tipos de errores incluyen una ubicación exacta con el siguiente formato: *[nombre del proyecto]* *[nombre del formulario]* línea:*[número de línea]* columna:*[número de columna]*. Si una pila de llamadas está asociada al error, puede hacer clic en el vínculo **Mostrar pila de llamadas** para verla. Examinar la pila de llamadas puede ayudarle a resolver el error.

![Error expandido Diseñador de Windows Forms](media/windows-forms-designer-error-page-expanded.png)

> [!NOTE]
>
> - En el caso de las aplicaciones Visual Basic, la página de errores en tiempo de diseño no muestra más de un error, pero puede mostrar varias instancias del mismo error.
> - En el caso de las aplicaciones de C++, los errores no tienen vínculos de ubicación de código.

## <a name="help-with-this-error"></a>Ayuda con este error

Si hay disponible un tema de ayuda para el error, haga clic en el vínculo **ayuda de MSDN** para ir directamente a la página de ayuda de docs.Microsoft.com.

## <a name="forum-posts-about-this-error"></a>Entradas del foro sobre este error

Haga clic en el vínculo **Buscar en MSDN foros sobre las publicaciones relacionadas con este error** para ir a los foros de Microsoft Developer Network. Puede que desee buscar específicamente en los foros de [Diseñador de Windows Forms](https://social.msdn.microsoft.com/Forums/windows/home?forum=winformsdesigner) o [Windows Forms](https://social.msdn.microsoft.com/Forums/windows/home?category=windowsforms) .

## <a name="design-time-errors"></a>Errores en tiempo de diseño

En esta sección se enumeran algunos de los errores que pueden producirse.

### <a name="identifier-name-is-not-a-valid-identifier"></a>' \<identifier name> ' no es un identificador válido

Este error indica que un campo, un método, un evento o un objeto tienen un nombre incorrecto.

### <a name="name-already-exists-in-project-name"></a>' \<name> ' ya existe en ' \<project name> '

Mensaje de error: "' ' \<name> ya existe en ' \<project name> '. Escriba un nombre único. "

Ha especificado un nombre para un formulario heredado que ya existe en el proyecto. Para corregir este error, asigne un nombre único al formulario heredado.

### <a name="toolbox-tab-name-is-not-a-toolbox-category"></a>' \<Toolbox tab name> ' no es una categoría de cuadro de herramientas

Un diseñador de terceros ha intentado tener acceso a una pestaña en el cuadro de herramientas que no existe. Póngase en contacto con el proveedor del componente.

### <a name="a-requested-language-parser-is-not-installed"></a>Un analizador de lenguaje solicitado no está instalado

Mensaje de error: "un analizador de lenguaje solicitado no está instalado. El nombre del analizador de lenguaje es ' {0} '.

Visual Studio intentó cargar un diseñador que está registrado para el tipo de archivo pero no pudo. Lo más probable es que se deba a un error que se produjo durante la instalación. Póngase en contacto con el proveedor del idioma que está usando para corregirlo.

### <a name="a-service-required-for-generating-and-parsing-source-code-is-missing"></a>Falta un servicio necesario para generar y analizar código fuente

Se trata de un problema con un componente de terceros. Póngase en contacto con el proveedor del componente.

### <a name="an-exception-occurred-while-trying-to-create-an-instance-of-object-name"></a>Se produjo una excepción al intentar crear una instancia de ' \<object name> '

Mensaje de error: "se produjo una excepción al intentar crear una instancia de ' \<object name> '. La excepción era " \<exception string\> ".

Un diseñador de terceros solicitó que Visual Studio creara un objeto, pero el objeto producía un error. Póngase en contacto con el proveedor del componente.

### <a name="another-editor-has-document-name-open-in-an-incompatible-mode"></a>Otro editor tiene \<document name> abierto ' ' en un modo no compatible

Mensaje de error: "otro editor tiene \<document name> abierto ' ' en un modo no compatible. Cierre el editor y vuelva a intentar esta operación ".

Este error se produce si intenta abrir un archivo que ya está abierto en otro editor. Se muestra el editor que ya tiene abierto el archivo. Para corregir este error, cierre el editor que tiene abierto el archivo y vuelva a intentarlo.

### <a name="another-editor-has-made-changes-to-document-name"></a>Otro editor ha realizado cambios en ' \<document name> '

Cierre y vuelva a abrir el diseñador para que los cambios surtan efecto. Normalmente, Visual Studio recarga automáticamente un diseñador una vez realizados los cambios. Sin embargo, es posible que otros diseñadores, como los diseñadores de componentes de terceros, no admitan el comportamiento de recarga. En este caso, Visual Studio le pide que cierre y vuelva a abrir el diseñador manualmente.

### <a name="another-editor-has-the-file-open-in-an-incompatible-mode"></a>Otro editor tiene abierto el archivo en modo incompatible

Mensaje de error: "otro editor tiene abierto el archivo en un modo no compatible. Cierre el editor y vuelva a intentar esta operación ".

Este mensaje es similar a "otro editor tiene \<document name> abierto ' ' en un modo no compatible", pero Visual Studio no puede determinar el nombre de archivo. Para corregir este error, cierre el editor que tiene abierto el archivo y vuelva a intentarlo.

### <a name="array-rank-rank-in-array-is-too-high"></a>El rango de la matriz ' \<rank in array> ' es demasiado alto

Visual Studio solo admite matrices de una sola dimensión en el bloque de código analizado por el diseñador. Las matrices multidimensionales son válidas fuera de esta área.

### <a name="assembly-assembly-name-could-not-be-opened"></a>No se pudo abrir el ensamblado ' \<assembly name> '

Mensaje de error: "no se pudo abrir el ensamblado ' \<assembly name> '. Compruebe que el archivo todavía existe. "

Este mensaje de error se produce cuando intenta abrir un archivo que no se puede abrir. Compruebe que el archivo existe y es un ensamblado válido.

### <a name="bad-element-type-this-serializer-expects-an-element-of-type-type-name"></a>Tipo de elemento incorrecto. Este serializador espera un elemento de tipo ' \<type name> '

Se trata de un problema con un componente de terceros. Póngase en contacto con el proveedor del componente.

### <a name="cannot-access-the-visual-studio-toolbox-at-this-time"></a>No se puede obtener acceso al Cuadro de herramientas de Visual Studio en este momento

Visual Studio realizó una llamada al cuadro de herramientas, que no estaba disponible. Si ve este error, si ve este error, registre un problema mediante el uso de [notificar un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="cannot-bind-an-event-handler-to-the-event-name-event-because-it-is-read-only"></a>No se puede enlazar un controlador de eventos al \<event name> evento ' ' porque es de solo lectura

Este error suele surgir cuando se intenta conectar un evento a un control que se hereda de una clase base. Si la variable miembro del control es privada, Visual Studio no puede conectar el evento al método. Los controles heredados de forma privada no pueden tener otros eventos enlazados a ellos.

### <a name="cannot-create-a-method-name-for-the-requested-component-because-it-is-not-a-member-of-the-design-container"></a>No se puede crear un nombre de método para el componente solicitado porque no es miembro del contenedor de diseño

Visual Studio ha intentado agregar un controlador de eventos a un componente que no tiene una variable miembro en el diseñador. Póngase en contacto con el proveedor del componente.

### <a name="cannot-name-the-object-name-because-it-is-already-named-name"></a>No se puede asignar el nombre al objeto ' \<name> ' porque ya tiene el nombre ' \<name> '

Se trata de un error interno en el serializador de Visual Studio. Indica que el serializador ha intentado asignar un nombre a un objeto dos veces, lo que no se admite. Si ve este error, registre un problema mediante el uso de [notificar un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="cannot-remove-or-destroy-inherited-component-component-name"></a>No se puede quitar o destruir el componente heredado ' \<component name> '

Los controles heredados están bajo la propiedad de su clase heredada. Los cambios en el control heredado deben realizarse en la clase desde la que se origina el control. Por lo tanto, no se puede cambiar el nombre ni destruirlo.

### <a name="category-toolbox-tab-name-does-not-have-a-tool-for-class-class-name"></a>La categoría ' \<Toolbox tab name> ' no tiene una herramienta para la clase ' \<class name> '

El diseñador ha intentado hacer referencia a una clase en una pestaña determinada del cuadro de herramientas, pero la clase no existe. Póngase en contacto con el proveedor del componente.

### <a name="class-class-name-has-no-matching-constructor"></a>La clase ' \<class name> ' no tiene ningún constructor coincidente

Un diseñador de terceros pidió a Visual Studio que creara un objeto con parámetros concretos en el constructor que no existe. Póngase en contacto con el proveedor del componente.

### <a name="code-generation-for-property-property-name-failed"></a>No se pudo generar el código para la propiedad ' \<property name> '

Se trata de un contenedor genérico para un error. La cadena de error que acompaña a este mensaje proporcionará más detalles sobre el mensaje de error y un vínculo a un tema de ayuda más específico. Para corregir este error, solucione el error especificado en el mensaje de error anexado a este error.

### <a name="component-component-name-did-not-call-containeradd-in-its-constructor"></a>El componente ' \<component name> ' no ha llamado a container. Add () en su constructor

Se trata de un error en el componente que acaba de cargar o colocar en el formulario. Indica que el componente no se agregó a su control contenedor (ya sea otro control o formulario). El diseñador seguirá funcionando, pero puede haber problemas con el componente en tiempo de ejecución.

Para corregir el error, póngase en contacto con el proveedor del componente. O bien, si es un componente creado, llame al `IContainer.Add` método en el constructor del componente.

### <a name="component-name-cannot-be-empty"></a>El nombre del componente no puede estar vacío

Este error se produce al intentar cambiar el nombre de un componente a un valor vacío.

### <a name="could-not-access-the-variable-variable-name-because-it-has-not-been-initialized-yet"></a>No se pudo obtener acceso a la variable ' \<variable name> ' porque aún no se ha inicializado

Este error puede producirse debido a dos escenarios. Un proveedor de componentes de terceros tiene un problema con un control o componente que han distribuido, o el código que ha escrito tiene dependencias recursivas entre los componentes.

Para corregir este error, asegúrese de que el código no tiene una dependencia recursiva. Si no tiene estos problemas, tenga en cuenta el texto exacto del mensaje de error y póngase en contacto con el proveedor del componente.

### <a name="could-not-find-type-type-name"></a>No se pudo encontrar el tipo ' \<type name> '

Mensaje de error: "no se pudo encontrar el tipo ' \<type name> '. Asegúrese de que se hace referencia al ensamblado que contiene este tipo. Si este tipo forma parte del proyecto de desarrollo, asegúrese de que el proyecto se ha creado correctamente. "

Este error se produjo porque no se encontró una referencia. Asegúrese de que se hace referencia al tipo indicado en el mensaje de error y que también se hace referencia a los ensamblados que requiere el tipo. A menudo, el problema es que no se ha creado un control de la solución. Para compilar, seleccione **compilar solución** en el menú **compilar** . En caso contrario, si el control ya se ha compilado, agregue una referencia manualmente en el menú contextual de la carpeta **referencias** o **dependencias** en explorador de soluciones.

### <a name="could-not-load-type-type-name"></a>No se pudo cargar el tipo ' \<type name> '

Mensaje de error: "no se pudo cargar el tipo ' \<type name> '. Asegúrese de que el ensamblado que contiene este tipo se agrega a las referencias del proyecto ".

Visual Studio intentó conectar un método de control de eventos y no encontró uno o más tipos de parámetros para el método. Esto suele deberse a que falta una referencia. Para corregir este error, agregue la referencia que contiene el tipo al proyecto e inténtelo de nuevo.

### <a name="could-not-locate-the-project-item-templates-for-inherited-components"></a>No se pudo encontrar las plantillas del elemento de proyecto de los componentes heredados

Las plantillas para los formularios heredados en Visual Studio no están disponibles. Si ve este error, registre un problema mediante el uso de [notificar un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="delegate-class-class-name-has-no-invoke-method-is-this-class-a-delegate"></a>La clase delegada ' \<class name> ' no tiene ningún método Invoke. ¿Es esta clase un delegado?

Visual Studio ha intentado crear un controlador de eventos, pero hay algún problema con el tipo de evento. Esto puede ocurrir si el evento se creó mediante un lenguaje no conforme a CLS. Póngase en contacto con el proveedor del componente.

### <a name="duplicate-declaration-of-member-member-name"></a>Declaración duplicada del miembro ' \<member name> '

Este error se produce porque una variable miembro se ha declarado dos veces (por ejemplo, `Button1` se declaran dos controles denominados en el código). Los nombres deben ser únicos en los formularios heredados. Además, los nombres no pueden diferir solo en caso.

### <a name="error-reading-resources-from-the-resource-file-for-the-culture-culture-name"></a>Error al leer los recursos del archivo de recursos para la referencia cultural ' \<culture name> '

Este error puede producirse si hay un archivo. resx incorrecto en el proyecto.

Para corregir dicho error:

1. Haga clic en el botón **Mostrar todos los archivos** de explorador de soluciones para ver los archivos. resx asociados a la solución.
2. Cargue el archivo. resx en el editor XML; para ello, haga clic con el botón secundario en el archivo. resx y elija **abrir**.
3. Edite el archivo. resx manualmente para solucionar los errores.

### <a name="error-reading-resources-from-the-resource-file-for-the-default-culture-culture-name"></a>Error al leer los recursos del archivo de recursos para la referencia cultural predeterminada ' \<culture name> '

Este error puede producirse si hay un archivo. resx incorrecto en el proyecto para la referencia cultural predeterminada.

Para corregir dicho error:

1. Haga clic en el botón **Mostrar todos los archivos** de explorador de soluciones para ver los archivos. resx asociados a la solución.
2. Cargue el archivo. resx en el editor XML; para ello, haga clic con el botón secundario en el archivo. resx y elija **abrir**.
3. Edite el archivo. resx manualmente para solucionar los errores.

### <a name="failed-to-parse-method-method-name"></a>No se pudo analizar el método ' \<method name> '

Mensaje de error: "no se pudo analizar el método ' \<method name> '. El analizador ha detectado el siguiente error: ' \<error string> '. Busque posibles errores en el Lista de tareas.

Se trata de un mensaje de error general para los problemas que surgen durante el análisis. Estos errores suelen deberse a errores de sintaxis. Vea el Lista de tareas para ver mensajes específicos relacionados con el error.

### <a name="invalid-component-name-component-name"></a>Nombre de componente no válido: ' \<component name> '

Ha intentado cambiar el nombre de un componente por un valor no válido para ese idioma. Para corregir este error, asigne al componente el nombre de modo que cumpla las reglas de nomenclatura para ese idioma.

### <a name="the-type-class-name-is-made-of-several-partial-classes-in-the-same-file"></a>El tipo ' \<class name> ' se compone de varias clases parciales en el mismo archivo

Al definir una clase en varios archivos mediante la palabra clave [partial](../../../csharp/language-reference/keywords/partial-type.md) , solo puede tener una definición parcial en cada archivo.

Para corregir este error, quite todas las definiciones parciales de la clase, excepto una, del archivo.

### <a name="the-assembly-assembly-name-could-not-be-found"></a>No se encontró el ensamblado ' \<assembly name> '

Mensaje de error: "no se encontró el ensamblado ' \<assembly name> '. Asegúrese de que se hace referencia al ensamblado. Si el ensamblado forma parte del proyecto de desarrollo actual, asegúrese de que se ha compilado el proyecto ".

Este error es similar a "no se pudo encontrar el tipo" " \<type name> , pero este error suele producirse debido a un atributo de metadatos. Para corregir este error, compruebe que se hace referencia a todos los ensamblados utilizados por los atributos.

### <a name="the-assembly-name-assembly-name-is-invalid"></a>El nombre de ensamblado ' \<assembly name> ' no es válido

Un componente ha solicitado un ensamblado determinado, pero el nombre proporcionado por el componente no es un nombre de ensamblado válido. Póngase en contacto con el proveedor del componente.

### <a name="the-base-class-class-name-cannot-be-designed"></a>\<class name>No se puede diseñar la clase base ' '

Visual Studio cargó la clase, pero la clase no se puede diseñar porque el implementador de la clase no proporcionó un diseñador. Si la clase admite un diseñador, asegúrese de que no hay ningún problema que pueda causar problemas al mostrarlo en un diseñador, como errores del compilador. Además, asegúrese de que todas las referencias a la clase sean correctas y de que todos los nombres de clase estén escritos correctamente. De lo contrario, si la clase no está diseñada, edítela en la vista Código.

### <a name="the-base-class-class-name-could-not-be-loaded"></a>No se pudo cargar la clase base ' \<class name> '

No se hace referencia a la clase en el proyecto, por lo que Visual Studio no puede cargarla. Para corregir este error, agregue una referencia a la clase en el proyecto y cierre y vuelva a abrir la ventana Diseñador de Windows Forms.

### <a name="the-class-class-name-cannot-be-designed-in-this-version-of-visual-studio"></a>La clase ' \<class name> ' no se puede diseñar en esta versión de Visual Studio

El diseñador de este control o componente no admite los mismos tipos que Visual Studio. Póngase en contacto con el proveedor del componente.

### <a name="the-class-name-is-not-a-valid-identifier-for-this-language"></a>El nombre de clase no es un identificador válido para este lenguaje

El código fuente que crea el usuario tiene un nombre de clase que no es válido para el idioma que se está usando. Para corregir este error, asigne un nombre a la clase de modo que se ajuste a los requisitos de idioma.

### <a name="the-component-cannot-be-added-because-it-contains-a-circular-reference-to-reference-name"></a>No se puede Agregar el componente porque contiene una referencia circular a ' \<reference name> '

No se puede Agregar un control o componente a sí mismo. Otra situación en la que esto puede ocurrir es que haya código en el método InitializeComponent de un formulario (por ejemplo, Form1) que cree otra instancia de Form1.

### <a name="the-designer-cannot-be-modified-at-this-time"></a>No se puede modificar el diseñador en este momento

Este error se produce cuando el archivo del editor está marcado como de solo lectura. Asegúrese de que el archivo no está marcado como de solo lectura y de que la aplicación no se está ejecutando.

### <a name="the-designer-could-not-be-shown-for-this-file-because-none-of-the-classes-within-it-can-be-designed"></a>No se puede mostrar el diseñador para este archivo porque ninguna de las clases que contiene se puede diseñar

Este error se produce cuando Visual Studio no puede encontrar una clase base que satisfaga los requisitos del diseñador. Los formularios y controles deben derivar de una clase base que admita diseñadores. Si va a derivar de un formulario o control heredado, asegúrese de que se ha compilado el proyecto.

### <a name="the-designer-for-base-class-class-name-is-not-installed"></a>El diseñador de la clase base ' \<class name> ' no está instalado

Visual Studio no pudo cargar el diseñador para la clase. Si ve este error, registre un problema mediante el uso de [notificar un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="the-designer-must-create-an-instance-of-type-type-name-but-it-cant-because-the-type-is-declared-as-abstract"></a>El diseñador debe crear una instancia de tipo ' \<type name> ', pero no puede porque el tipo se declara como abstracto

Este error se produjo porque la clase base del objeto que se pasa al diseñador es [abstracta](../../../csharp/language-reference/keywords/abstract.md), lo que no está permitido.

### <a name="the-file-could-not-be-loaded-in-the-designer"></a>No se puede cargar el archivo en el diseñador

La clase base de este archivo no admite ningún diseñador. Como solución alternativa, use la vista Código para trabajar en el archivo. Haga clic con el botón derecho en el archivo en Explorador de soluciones y elija **Ver código**.

### <a name="the-language-for-this-file-does-not-support-the-necessary-code-parsing-and-generation-services"></a>El lenguaje de este archivo no admite los servicios de análisis y generación de código necesarios

Mensaje de error: "el idioma de este archivo no admite los servicios de análisis y generación de código necesarios. Asegúrese de que el archivo que está abriendo es miembro de un proyecto y, a continuación, intente abrir el archivo de nuevo. "

Lo más probable es que este error se deba a la apertura de un archivo que se encuentra en un proyecto que no admite diseñadores.

### <a name="the-language-parser-class-class-name-is-not-implemented-properly"></a>La clase del analizador de lenguaje ' \<class name> ' no se ha implementado correctamente

Mensaje de error: "la clase del analizador de lenguaje ' \<class name> ' no se ha implementado correctamente. Póngase en contacto con el proveedor para obtener un módulo de analizador actualizado. "

El lenguaje en uso ha registrado una clase de diseñador que no se deriva de la clase base correcta. Póngase en contacto con el proveedor del idioma que está usando.

### <a name="the-name-name-is-already-used-by-another-object"></a>\<name>Otro objeto ya utiliza el nombre ' '

Se trata de un error interno en el serializador de Visual Studio. Si ve este error, registre un problema mediante el uso de [notificar un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="the-object-object-name-does-not-implement-the-icomponent-interface"></a>El objeto ' \<object name> ' no implementa la interfaz IComponent

Visual Studio intentó crear un componente, pero el objeto creado no implementa la <xref:System.ComponentModel.IComponent> interfaz. Póngase en contacto con el proveedor del componente para obtener una corrección.

### <a name="the-object-object-name-returned-null-for-the-property-property-name-but-this-is-not-allowed"></a>El objeto ' \<object name> ' devolvió null para la propiedad ' \<property name> ', pero esto no se permite

Hay algunas propiedades de .NET que siempre deben devolver un objeto. Por ejemplo, la colección de **controles** de un formulario siempre debe devolver un objeto, incluso cuando no hay controles en él.

Para corregir este error, asegúrese de que la propiedad especificada en el error no sea NULL.

### <a name="the-serialization-data-object-is-not-of-the-proper-type"></a>El objeto de datos de serialización no es del tipo correcto

Un objeto de datos ofrecido por el serializador no es una instancia de un tipo que coincida con el serializador actual que se está usando. Póngase en contacto con el proveedor del componente.

### <a name="the-service-service-name-is-required-but-could-not-be-located"></a>El servicio ' \<service name> ' es obligatorio, pero no se encontró

Mensaje de error: "el servicio ' \<service name> ' es obligatorio, pero no se encontró. Puede haber un problema con la instalación de Visual Studio ".

Un servicio requerido por Visual Studio no está disponible. Si intenta cargar un proyecto que no admite ese diseñador, use el editor de código para realizar los cambios necesarios. De lo contrario, si ve este error, registre un problema mediante el uso de [notificar un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="the-service-instance-must-derive-from-or-implement-interface-name"></a>La instancia de servicio debe derivar de o implementar ' \<interface name> '

Este error indica que un componente o diseñador de componentes ha llamado al método **AddService** , que requiere una interfaz y un objeto, pero el objeto especificado no implementa la interfaz especificada. Póngase en contacto con el proveedor del componente.

### <a name="the-text-in-the-code-window-could-not-be-modified"></a>El texto de la ventana de código no puede modificarse

Mensaje de error: "no se pudo modificar el texto de la ventana de código. Compruebe que el archivo no sea de solo lectura y que haya suficiente espacio en disco. "

Este error se produce cuando Visual Studio no puede editar un archivo debido a problemas de espacio en disco o de memoria, o el archivo está marcado como de solo lectura.

### <a name="the-toolbox-enumerator-object-only-supports-retrieving-one-item-at-a-time"></a>El objeto enumerador del cuadro de herramientas sólo admite recuperar un elemento cada vez

Si ve este error, si ve este error, registre un problema mediante el uso de [notificar un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="the-toolbox-item-for-component-name-could-not-be-retrieved-from-the-toolbox"></a>No se pudo recuperar el elemento del cuadro de herramientas para ' \<component name> ' desde el cuadro de herramientas

Mensaje de error: "no se pudo recuperar el elemento del cuadro de herramientas para ' \<component name> ' desde el cuadro de herramientas. Asegúrese de que el ensamblado que contiene el elemento del cuadro de herramientas está correctamente instalado. El elemento del cuadro de herramientas ha generado el siguiente error: \<error string> . "

El componente en cuestión produjo una excepción cuando Visual Studio tuvo acceso a ella. Póngase en contacto con el proveedor del componente.

### <a name="the-toolbox-item-for-toolbox-item-name-could-not-be-retrieved-from-the-toolbox"></a>No se pudo recuperar el elemento del cuadro de herramientas para ' \<Toolbox item name> ' desde el cuadro de herramientas

Mensaje de error: "no se pudo recuperar el elemento del cuadro de herramientas para ' \<Toolbox item name> ' desde el cuadro de herramientas. Intente quitar el elemento del cuadro de herramientas y volver a agregarlo. "

Este error se produce si los datos del elemento del cuadro de herramientas se dañan o la versión del componente ha cambiado. Intente quitar el elemento del cuadro de herramientas y volver a agregarlo.

### <a name="the-type-type-name-could-not-be-found"></a>No se pudo encontrar el tipo ' \<type name> '

Mensaje de error: "no se \<type name> pudo encontrar el tipo ' '. Asegúrese de que se hace referencia al ensamblado que contiene el tipo. Si el ensamblado forma parte del proyecto de desarrollo actual, asegúrese de que se ha compilado el proyecto ".

Al cargar el diseñador, Visual Studio no encontró un tipo. Asegúrese de que se hace referencia al ensamblado que contiene el tipo. Si el ensamblado forma parte del proyecto de desarrollo actual, asegúrese de que se ha compilado el proyecto.

### <a name="the-type-resolution-service-may-only-be-called-from-the-main-application-thread"></a>Sólo se puede llamar al servicio de resolución de tipos desde el subproceso de la aplicación principal

Visual Studio intentó tener acceso a los recursos necesarios desde el subproceso equivocado. Este error se muestra cuando el código utilizado para crear el diseñador ha llamado al servicio de resolución de tipos desde un subproceso distinto del subproceso de aplicación principal. Para corregir este error, llame al servicio desde el subproceso correcto o póngase en contacto con el proveedor del componente.

### <a name="the-variable-variable-name-is-either-undeclared-or-was-never-assigned"></a>La variable ' \<variable name> ' no está declarada o no se ha asignado nunca

El código fuente tiene una referencia a una variable, como **button1**, que no se ha declarado o asignado. Si no se ha asignado la variable, este mensaje aparece como una advertencia, no como un error.

### <a name="there-is-already-a-command-handler-for-the-menu-command-menu-command-name"></a>Ya existe un controlador de comandos para el comando de menú ' \<menu command name> '

Este error se produce si un diseñador de terceros agrega un comando que ya tiene un controlador a la tabla de comandos. Póngase en contacto con el proveedor del componente.

### <a name="there-is-already-a-component-named-component-name"></a>Ya existe un componente denominado ' \<component name> '

Mensaje de error: "ya existe un componente con el nombre" \<component name> ". Los componentes deben tener nombres únicos y los nombres no deben distinguir entre mayúsculas y minúsculas. Un nombre tampoco puede entrar en conflicto con el nombre de cualquier componente de una clase heredada ".

Este mensaje de error se produce cuando se ha producido un cambio en el nombre de un componente en el ventana Propiedades. Para corregir este error, asegúrese de que todos los nombres de componente son únicos, no distinguen mayúsculas de minúsculas y no entran en conflicto con los nombres de los componentes de las clases heredadas.

### <a name="there-is-already-a-toolbox-item-creator-registered-for-the-format-format-name"></a>Ya hay un creador de elementos de cuadro de herramientas registrado para el formato ' \<format name> '

Un componente de terceros realizó una devolución de llamada a un elemento en una pestaña del cuadro de herramientas, pero el elemento ya contenía una devolución de llamada. Póngase en contacto con el proveedor del componente.

### <a name="this-language-engine-does-not-support-a-codemodel-with-which-to-load-a-designer"></a>Este motor de lenguaje no es compatible con un modelo de código con el que cargar un diseñador

Este mensaje es similar a "el lenguaje de este archivo no admite los servicios de análisis y generación de código necesarios", pero este mensaje implica un problema de registro interno. Si ve este error, si ve este error, registre un problema mediante el uso de [notificar un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="type-type-name-does-not-have-a-constructor-with-parameters-of-types-parameter-type-names"></a>El tipo ' \<type name\> ' no tiene un constructor con parámetros de tipos ' \<parameter type names> '

Visual Studio no encontró un [constructor](../../../csharp/programming-guide/classes-and-structs/constructors.md) que tuviera parámetros coincidentes. Esto puede ser el resultado de proporcionar un constructor con tipos distintos de los necesarios. Por ejemplo, un constructor de **puntos** puede tomar dos enteros. Si proporcionó Float, se genera este error.

Para corregir este error, use un constructor diferente o convierta explícitamente los tipos de parámetro de modo que coincidan con los proporcionados por el constructor.

### <a name="unable-to-add-reference-reference-name-to-the-current-application"></a>No se puede Agregar la referencia ' \<reference name> ' a la aplicación actual

Mensaje de error: "no se puede agregar \<reference name> la referencia ' ' a la aplicación actual. Compruebe que \<reference name> ya no se hace referencia a una versión diferente de ' '.

Visual Studio no puede Agregar una referencia. Para corregir este error, compruebe que todavía no se hace referencia a una versión diferente de la referencia.

### <a name="unable-to-check-out-the-current-file"></a>No se puede desproteger el archivo actual

Mensaje de error: "no se puede desproteger el archivo actual. Es posible que el archivo esté bloqueado o que sea necesario desproteger el archivo manualmente ".

Este error se produce cuando se cambia un archivo protegido actualmente en el control de código fuente. Normalmente, Visual Studio muestra el cuadro de diálogo de desprotección de archivos para que el usuario pueda desproteger el archivo. Esta vez, el archivo no se desprotegió, quizás debido a un conflicto de combinación durante la desprotección. Para corregir este error, asegúrese de que el archivo no esté bloqueado y, a continuación, intente desproteger el archivo manualmente.

### <a name="unable-to-find-page-named-options-dialog-box-tab-name"></a>No se puede encontrar la página con el nombre ' \<Options dialog box tab name> '

Este error se produce cuando un diseñador de componentes solicita acceso a una página del cuadro de diálogo Opciones con un nombre que no existe. Póngase en contacto con el proveedor del componente.

### <a name="unable-to-find-property-property-name-on-page-options-dialog-box-tab-name"></a>No se puede encontrar la propiedad ' \<property name> ' en la página ' \<Options dialog box tab name> '

Este error se produce cuando un diseñador de componentes solicita acceso a un valor determinado en una página del cuadro de diálogo Opciones, pero ese valor no existe. Póngase en contacto con el proveedor del componente.

### <a name="visual-studio-cannot-open-a-designer-for-the-file-because-the-class-within-it-does-not-inherit-from-a-class-that-can-be-visually-designed"></a>Visual Studio no puede abrir un diseñador para el archivo porque la clase incluida no hereda de ninguna clase que se pueda diseñar visualmente

Visual Studio cargó la clase, pero el diseñador de esa clase no se pudo cargar. Visual Studio requiere que los diseñadores usen la primera clase en un archivo. Para corregir este error, mueva el código de la clase para que sea la primera clase del archivo y, a continuación, vuelva a cargar el diseñador.

### <a name="visual-studio-cannot-save-or-load-instances-of-the-type-type-name"></a>Visual Studio no puede guardar o cargar instancias del tipo ' \<type name> '

Se trata de un problema con un componente de terceros. Póngase en contacto con el proveedor del componente.

### <a name="visual-studio-is-unable-to-open-document-name-in-design-view"></a>Visual Studio no puede abrir ' \<document name> ' en vista de diseño

Mensaje de error: "Visual Studio no puede abrir ' \<document name> ' en vista de diseño. No hay ningún analizador instalado para el tipo de archivo ".

Este error indica que el idioma del proyecto no es compatible con un diseñador y se produce cuando se intenta abrir un archivo en el cuadro de diálogo Abrir archivo o en Explorador de soluciones. En su lugar, edite el archivo en la vista de código.

### <a name="visual-studio-was-unable-to-find-a-designer-for-classes-of-type-type-name"></a>Visual Studio no pudo encontrar un diseñador para las clases de tipo ' \<type name> '

Visual Studio cargó la clase, pero la clase no se puede diseñar. En su lugar, edite la clase en la vista Código; para ello, haga clic con el botón secundario en la clase y elija **Ver código**.

## <a name="see-also"></a>Consulte también

- [Desarrollo de Windows Forms controles mediante el diseñador](developing-windows-forms-controls-at-design-time.md)
- [Foro de Diseñador de Windows Forms](https://social.msdn.microsoft.com/Forums/windows/home?forum=winformsdesigner)

---
title: Errores en tiempo de diseño en el Diseñador de Windows Forms
ms.date: 03/30/2017
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: cce9baf1523391e281593428b633c401103b42b5
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015968"
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a>Errores en tiempo de diseño en el Diseñador de Windows Forms

En este tema se explica el significado y el uso de la lista de errores en tiempo de diseño que aparece en Visual Studio cuando no se puede cargar el Diseñador de Windows Forms. Si esta lista de errores aparece, no debe interpretarse como un error del diseñador, sino como una ayuda para corregir errores en el código.

Un conocimiento básico de esta lista de errores le ayudará a depurar las aplicaciones brindando información detallada sobre los errores y sugerir posibles soluciones.

## <a name="the-design-time-error-list-interface"></a>La interfaz de la lista de errores en tiempo de diseño

Si no se puede cargar el Diseñador de Windows Forms, aparece una lista de errores en el diseñador. Los errores se agrupan en categorías. Por ejemplo, si tiene cuatro instancias de variables no declaradas, se agruparán en la misma categoría de error. Cada categoría de error incluye una breve descripción del error.

Puede expandir o contraer una categoría de error haciendo clic en el encabezado de la categoría de error o en el botón de contenido adicional de expandir o contraer. Al expandir una categoría de error, se muestra la ayuda adicional siguiente:

- Instancias del error.

- Ayuda con el error.

- Entradas del foro sobre el error.

### <a name="instances-of-this-error"></a>Instancias de este error

La lista de ayuda adicional muestra todas las instancias del error en el proyecto actual. Muchos errores incluyen una ubicación exacta en el formato siguiente: *[nombre de proyecto]* *[nombre del formulario]* línea: *[número de línea]* columna: *[número de columna]* . El vínculo **Ir al código** le lleva a la ubicación del código donde se produce el error.

Si se asocia una pila de llamadas al error, puede hacer clic en el vínculo **Mostrar pila de llamadas**, lo que amplía aún más el error para mostrar la pila de llamadas. El examen de la pila puede ofrecer información valiosa sobre depuración. Por ejemplo, puede realizar el seguimiento de las funciones que se llamaron antes de producirse el error. La pila de llamadas es seleccionable para que se pueda copiar y guardarla.

> [!NOTE]
> En Visual Basic, la lista de errores en tiempo de diseño no muestra más que un error, pero puede mostrar varias instancias del mismo error. En Visual C++, los errores no tienen vínculos para ir al código ni vínculos de números de línea.

### <a name="forum-posts-about-this-error"></a>Entradas del foro sobre este error

La ayuda adicional incluye un vínculo a las entradas del Foro relacionadas con el error. Los foros se buscan por la cadena del mensaje de error. También puede intentar buscar en los foros siguientes:

- [Foro de Diseñador de Windows Forms](https://social.msdn.microsoft.com/Forums/windows/home?forum=winformsdesigner)

- [Foro de Windows Forms](https://social.msdn.microsoft.com/Forums/windows/home?category=windowsforms)

### <a name="ignore-and-continue"></a>Omitir y continuar

Puede omitir la condición de error y seguir cargando el diseñador. La elección de esta acción puede dar lugar a un comportamiento inesperado. Por ejemplo, puede que no aparezcan controles en la superficie de diseño.

## <a name="see-also"></a>Vea también

- [Solución de problemas de desarrollo en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))
- [Solución de problemas relacionados con la creación de controles y componentes](troubleshooting-control-and-component-authoring.md)
- [Desarrollar controles de Windows Forms en tiempo de diseño](developing-windows-forms-controls-at-design-time.md)
- [Windows Forms Designer Error Messages](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100)) (Mensajes de error del Diseñador de Windows Forms)

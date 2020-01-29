---
title: Escalado automático
ms.date: 06/15/2017
helpviewer_keywords:
- scalability [Windows Forms], automatic in Windows Forms
- Windows Forms, automatic scaling
ms.assetid: 68fad25b-afbc-44bd-8e1b-966fc43507a4
ms.openlocfilehash: 96dbbb5ed20027e25f1bde89748710766ec06506
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732379"
---
# <a name="automatic-scaling-in-windows-forms"></a>Escalado automático en Windows Forms

El escalado automático permite que un formulario y sus respectivos controles, diseñados en una máquina con una determinada resolución de pantalla o fuente del sistema, se muestren correctamente en otra máquina con una resolución de pantalla o una fuente de sistema diferentes. El escalado automático garantiza que el formulario y sus controles cambien de tamaño para mantener la coherencia con las ventanas nativas y otras aplicaciones tanto en máquinas de los usuarios como en las de otros desarrolladores. La compatibilidad del .NET Framework para el escalado automático y los estilos visuales permite que las aplicaciones .NET Framework mantengan una apariencia coherente en comparación con aplicaciones Windows nativas en el equipo de cada usuario.

En su mayor parte, el escalado automático funciona según lo previsto en .NET Framework versión 2,0 y posteriores. Sin embargo, los cambios en la combinación de fuentes pueden causar problemas. Para obtener un ejemplo de cómo resolver este error, consulte [Cómo: responder a los cambios de la combinación de fuentes en una aplicación Windows Forms](how-to-respond-to-font-scheme-changes-in-a-windows-forms-application.md).

## <a name="need-for-automatic-scaling"></a>Necesidad de escalado automático

Sin escalado automático, una aplicación diseñada para una fuente o una resolución de pantalla aparecerá demasiado pequeña o demasiado grande cuando se cambie la fuente o la resolución. Por ejemplo, si la aplicación está diseñada con Tahoma de 9 puntos como línea base, sin el ajuste aparecerá demasiado pequeña si se ejecuta en una máquina donde la fuente de sistema sea Tahoma de 12 puntos. Los elementos de texto, como títulos, menús, el contenido de cuadros de texto, etc. se representarán más pequeños que en otras aplicaciones. Además, el tamaño de los elementos de interfaz de usuario (UI) que contienen texto —como la barra de título, los menús y muchos controles— depende de la fuente usada. En este ejemplo, estos elementos también aparecerán relativamente más pequeños.

Una situación análoga se produce cuando se diseña una aplicación para una determinada resolución de pantalla. La resolución de pantalla más común es de 96 puntos por pulgada (PPP), que es igual a la escala de visualización 100%, pero la resolución más alta muestra la compatibilidad con 125%, 150%, 200% (que respectivamente son iguales a 120, 144 y 192 PPP) y versiones posteriores son más comunes. Si no se ajusta la escala de una aplicación diseñada para una resolución —especialmente si se trata de una aplicación basada en gráficos—, dicha aplicación se verá demasiado grande o demasiado pequeña cuando se ejecute a otra resolución.

El escalado automático busca mejorar estos problemas con un cambio automático el tamaño del formulario y de sus controles secundarios, de acuerdo con el tamaño de fuente o la resolución de pantalla relativos. El sistema operativo Windows admite el escalado automático de cuadros de diálogo mediante una unidad relativa de medida denominada unidades de cuadro de diálogo. Una unidad de cuadro de diálogo se basa en la fuente del sistema y su relación con los píxeles se puede determinar mediante la función del SDK de Win32 `GetDialogBaseUnits`. Cuando un usuario cambia el tema usado por Windows, todos los cuadros de diálogo se ajustan automáticamente según corresponda. Además, el .NET Framework admite el escalado automático según la fuente predeterminada del sistema o la resolución de pantalla. Opcionalmente, el escalado automático se puede deshabilitar en una aplicación.

## <a name="original-support-for-automatic-scaling"></a>Compatibilidad original con el escalado automático

Las versiones 1,0 y 1,1 del .NET Framework admiten el escalado automático de una manera sencilla que dependía de la fuente predeterminada de Windows usada para la interfaz de usuario, representada por el valor del SDK de Win32 **DEFAULT_GUI_FONT**. Por lo general, esta fuente solo se cambia cuando se modifica la resolución de pantalla. El mecanismo siguiente se usó para implementar el escalado automático:

1. En tiempo de diseño, la propiedad <xref:System.Windows.Forms.Form.AutoScaleBaseSize%2A> (que ahora está en desuso) se estableció en el alto y ancho de la fuente predeterminada del sistema en la máquina del desarrollador.

2. En runtime, la fuente predeterminada del sistema de la máquina del usuario se usaba para inicializar la propiedad <xref:System.Windows.Forms.Control.Font%2A> de la clase <xref:System.Windows.Forms.Form>.

3. Antes de mostrar el formulario, se llamaba al método <xref:System.Windows.Forms.Form.ApplyAutoScaling%2A> para escalar el formulario. Este método calculaba los tamaños de escala relativa de <xref:System.Windows.Forms.Form.AutoScaleBaseSize%2A> y <xref:System.Windows.Forms.Control.Font%2A> y, a continuación, se llamaba al método <xref:System.Windows.Forms.Control.Scale%2A> para escalar el formulario y sus elementos secundarios.

4. El valor de <xref:System.Windows.Forms.Form.AutoScaleBaseSize%2A> se actualizaba para que las siguientes llamadas a <xref:System.Windows.Forms.Form.ApplyAutoScaling%2A> no cambiaran progresivamente el tamaño del formulario.

Aunque este mecanismo era suficiente para la mayoría de los propósitos, sufría las limitaciones siguientes:

- Dado que la propiedad <xref:System.Windows.Forms.Form.AutoScaleBaseSize%2A> representa el tamaño de fuente de línea base como valores enteros, se producen errores de redondeo que se vuelven evidentes cuando un formulario se recorre en varias resoluciones.

- El escalado automático se implementó solo en la clase <xref:System.Windows.Forms.Form>, no en la clase <xref:System.Windows.Forms.ContainerControl>. Como resultado, los controles de usuario solo se escalaban correctamente si el control de usuario estaba diseñado con la misma resolución que el formulario y se colocaba en el formulario en tiempo de diseño.

- Los formularios y sus controles secundarios solo podían diseñarse de manera simultánea por varios desarrolladores si las resoluciones de sus máquinas eran iguales. Igualmente, hacía que la herencia de un formulario dependiese de la resolución asociada con el formulario principal.

- No es compatible con los administradores de diseño más recientes que se introdujeron con la versión .NET Framework 2,0, como <xref:System.Windows.Forms.FlowLayoutPanel> y <xref:System.Windows.Forms.TableLayoutPanel>.

- No admitía el escalado basado directamente en la resolución de pantalla necesaria para la compatibilidad con el .NET Compact Framework.

Aunque este mecanismo se conserva en la .NET Framework versión 2,0 para mantener la compatibilidad con versiones anteriores, se ha sustituido por el mecanismo de escalado más sólido que se describe a continuación. En consecuencia, <xref:System.Windows.Forms.Form.AutoScale%2A>, <xref:System.Windows.Forms.Form.ApplyAutoScaling%2A>, <xref:System.Windows.Forms.Form.AutoScaleBaseSize%2A> y determinadas sobrecargas <xref:System.Windows.Forms.Control.Scale%2A> están marcadas como obsoletas.

> [!NOTE]
> Puede eliminar de forma segura las referencias a estos miembros cuando actualice el código heredado a la .NET Framework versión 2,0.

## <a name="current-support-for-automatic-scaling"></a>Compatibilidad actual con el escalado automático

La .NET Framework versión 2,0 supera las limitaciones anteriores introduciendo los cambios siguientes en el escalado automático de Windows Forms:

- El soporte básico para el escalado se ha movido a la clase <xref:System.Windows.Forms.ContainerControl> para que los formularios, los controles compuestos nativos y los controles de usuario reciban soporte de escalado uniforme. Se han agregado los nuevos miembros <xref:System.Windows.Forms.ContainerControl.AutoScaleFactor%2A>, <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>, <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> y <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>.

- La clase <xref:System.Windows.Forms.Control> también tiene varios miembros nuevos que le permiten participar en el escalado y admitir escalado mixto en el mismo formulario. Concretamente, los miembros <xref:System.Windows.Forms.Control.Scale%2A>, <xref:System.Windows.Forms.Control.ScaleChildren%2A> y <xref:System.Windows.Forms.Control.GetScaledBounds%2A> admiten el escalado.

- Se ha agregado soporte de escalado basado en la resolución de pantalla para complementar el soporte de fuentes del sistema, tal como se define en la enumeración <xref:System.Windows.Forms.AutoScaleMode>. Este modo es compatible con el escalado automático admitido por el .NET Compact Framework habilitando la migración de aplicaciones más sencilla.

- Se ha agregado compatibilidad con administradores de diseño como <xref:System.Windows.Forms.FlowLayoutPanel> y <xref:System.Windows.Forms.TableLayoutPanel> a la implementación del escalado automático.

- Los factores de escalado se representan ahora como valores de número de punto flotante, normalmente mediante la estructura <xref:System.Drawing.SizeF>, con lo que prácticamente se han eliminado los errores de redondeo.

> [!CAUTION]
> No se admiten combinaciones arbitrarias de los modos de escalado de DPI y fuente. Aunque puede escalar sin ningún problema un control de usuario usando un modo (por ejemplo, DPI) y colocarlo en un formulario usando otro modo (Font), la combinación de un formulario base en un modo y un formulario derivado en otro puede provocar resultados inesperados.

### <a name="automatic-scaling-in-action"></a>Escalado automático en acción

Windows Forms ahora usa la lógica siguiente para escalar automáticamente los formularios y su contenido:

1. En tiempo de diseño, cada <xref:System.Windows.Forms.ContainerControl> registra el modo de escalado y su resolución actual en <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> y <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>, respectivamente.

2. En tiempo de ejecución, la resolución real se almacena en la propiedad <xref:System.Windows.Forms.ContainerControl.CurrentAutoScaleDimensions%2A>. La propiedad <xref:System.Windows.Forms.ContainerControl.AutoScaleFactor%2A> calcula dinámicamente la proporción entre la resolución de escalado en tiempo de ejecución y tiempo de diseño.

3. Si al cargar el formulario los valores de <xref:System.Windows.Forms.ContainerControl.CurrentAutoScaleDimensions%2A> y <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> son diferentes, se llamará al método <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A> para escalar el control y sus elementos secundarios. Este método suspende el diseño y llama al método <xref:System.Windows.Forms.Control.Scale%2A> para realizar el escalado real. Después, el valor de <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> se actualiza para evitar el escalado progresivo.

4. <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A> también se invoca automáticamente en las situaciones siguientes:

    - En respuesta al evento <xref:System.Windows.Forms.Control.OnFontChanged%2A> si el modo de escalado es <xref:System.Windows.Forms.AutoScaleMode.Font>.

    - Cuando el diseño del contenedor se reanuda y se detecta un cambio en las propiedades <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> o <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>.

    - Como se insinúa anteriormente, cuando se escala un elemento primario <xref:System.Windows.Forms.ContainerControl>. Cada control contenedor es responsable de realizar el escalado de sus elementos secundarios mediante sus propios factores de escala, no los del contenedor primario.

5. Los controles secundarios pueden modificar su comportamiento de escalado a través de varios medios:

    - La propiedad <xref:System.Windows.Forms.Control.ScaleChildren%2A> se puede invalidar para determinar si se deben escalar sus controles secundarios o no.

    - El método <xref:System.Windows.Forms.Control.GetScaledBounds%2A> se puede invalidar para ajustar los límites a los que se escala el control, pero no la lógica de escalado.

    - El método <xref:System.Windows.Forms.Control.ScaleControl%2A> se puede invalidar para cambiar la lógica de escalado del control actual.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>
- <xref:System.Windows.Forms.Control.Scale%2A>
- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>
- [Representar controles con estilos visuales](./controls/rendering-controls-with-visual-styles.md)
- [Procedimiento para mejorar el rendimiento evitando el ajuste de tamaño automático](./advanced/how-to-improve-performance-by-avoiding-automatic-scaling.md)

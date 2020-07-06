---
ms.openlocfilehash: d420be76645fc71ac922542fa49f799a473e9a83
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614855"
---
### <a name="accessibility-improvements-in-windows-workflow-foundation-wf-workflow-designer"></a>Mejoras de accesibilidad en el Diseñador de flujo de trabajo de Windows Workflow Foundation (WF)

#### <a name="details"></a>Detalles

El Diseñador de flujo de trabajo de Windows Workflow Foundation (WF) mejora su funcionamiento con tecnologías de accesibilidad. Estas mejoras incluyen los cambios siguientes:

- Se cambia el orden de tabulación de izquierda a derecha y de arriba a abajo en algunos controles:
- La ventana Inicializar correlación para establecer los datos de correlación para la actividad <xref:System.ServiceModel.Activities.InitializeCorrelation>.
- La ventana Definición de contenido para las actividades <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> y <xref:System.ServiceModel.Activities.ReceiveReply>.
- Hay más funciones disponibles a través del teclado:
- Al editar las propiedades de una actividad, los grupos de propiedades se pueden contraer mediante el teclado la primera vez que obtienen el foco.
- Ahora los iconos de advertencia son accesibles mediante el teclado.
- Ahora el botón Más propiedades de la ventana Propiedades es accesible mediante el teclado.
- Los usuarios del teclado ahora pueden tener acceso a los elementos de encabezado en los paneles Argumentos y Variables del Diseñador de flujo de trabajo.
- Visibilidad mejorada de los elementos con el foco, por ejemplo cuando:
- Se agregan filas a las cuadrículas de datos usadas por los diseñadores de actividad y el Diseñador de flujo de trabajo.
- Desplazamiento entre campos en las actividades <xref:System.ServiceModel.Activities.ReceiveReply> y <xref:System.ServiceModel.Activities.SendReply>.
- Establecimiento de valores predeterminados para variables o argumentos.
- Los lectores de pantalla ahora pueden reconocer correctamente:
- Los puntos de interrupción establecidos en el Diseñador de flujo de trabajo.
- Las actividades <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> y <xref:System.ServiceModel.Activities.CorrelationScope>.
- El contenido de la actividad <xref:System.ServiceModel.Activities.Receive>.
- El tipo de destino para la actividad <xref:System.Activities.Statements.InvokeMethod>.
- El cuadro combinado Excepción y la sección Finally de la actividad <xref:System.Activities.Statements.TryCatch>.
- El cuadro combinado Tipo de mensaje, el divisor de la ventana Agregar inicializadores de correlación, la ventana Definición de contenido y la ventana Definición de CorrelatesOn en las actividades de mensajería (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> y <xref:System.ServiceModel.Activities.ReceiveReply>).
- Transiciones a máquina de estados y destinos de transición.
- Anotaciones y conectores en las actividades <xref:System.Activities.Statements.FlowDecision>.
- Los menús contextuales (clic con el botón derecho) para las actividades.
- Los editores de valor de propiedad, el botón Borrar búsqueda, los botones de ordenación Por categoría y Alfabético, y el cuadro de diálogo Editor de expresiones en la cuadrícula de propiedades.
- El porcentaje de zoom en el Diseñador de flujo de trabajo.
- El separador en las actividades <xref:System.Activities.Statements.Parallel> y <xref:System.Activities.Statements.Pick>.
- La actividad <xref:System.Activities.Statements.InvokeDelegate>.
- La ventana Seleccionar tipos para las actividades de diccionario (`Microsoft.Activities.AddToDictionary&lt;TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary&lt;TKey,TValue>`, etc.).
- La ventana Examinar y seleccionar un tipo .NET.
- Rutas de navegación en el Diseñador de flujo de trabajo.
- Los usuarios que elijan temas de contraste alto verán muchas mejoras en la visibilidad del Diseñador de flujo de trabajo y sus controles, como relaciones de contraste mejoradas entre los elementos y cuadros de selección más evidentes para los elementos del foco.

#### <a name="suggestion"></a>Sugerencia

Si tiene una aplicación con un diseñador de flujo de trabajo rehospedado, se puede beneficiar de estos cambios si se realiza cualquiera de estas acciones:

- Volver a compilar la aplicación para destinarla a .NET Framework 4.7.1. Estos cambios de accesibilidad están habilitados de forma predeterminada.
- Si la aplicación tiene como destino .NET Framework 4.7 o una versión anterior, pero se ejecuta en .NET Framework 4.7.1, puede rechazar estos comportamientos de accesibilidad heredados si agrega el [conmutador de AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección `<runtime>` del archivo app.config de archivos y lo establece en `false`, como se muestra en el ejemplo siguiente.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
  </runtime>
</configuration>
```

En las aplicaciones destinadas a .NET Framework 4.7.1 o una versión posterior, y en las que se quiere conservar el comportamiento de accesibilidad heredado, se puede participar en el uso de las características de accesibilidad heredadas si se establece explícitamente este modificador de AppContext en `true`.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.7.1       |
| Tipo    | Redestinación |

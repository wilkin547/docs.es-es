---
title: 'Cómo: Escribir el registro de eventos de una aplicación'
ms.date: 07/20/2015
helpviewer_keywords:
- Computer.EventLog element
- WriteEntry method [Visual Basic]
- My.Computer.EventLog element
- event logs, writing to
ms.assetid: cadbc8c1-87af-4746-934e-55b79a4f6e2b
ms.openlocfilehash: 511bb8fb16851872c1a16ae7627ed0fc6594337c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74352044"
---
# <a name="how-to-write-to-an-application-event-log-visual-basic"></a>Cómo: Escribir en el registro de eventos de una aplicación (Visual Basic)

Puede usar los objetos `My.Application.Log` y `My.Log` para escribir información sobre los eventos que se producen en su aplicación. En este ejemplo se muestra cómo configurar un agente de escucha de registro de eventos para que `My.Application.Log` escriba información de seguimiento en el registro de eventos de la aplicación.

No se puede escribir en el registro de seguridad. Para poder escribir en el registro del sistema, debe ser miembro de la cuenta LocalSystem o Administrador.

Para ver un registro de eventos, puede usar el **Explorador de servidores** o el **Visor de eventos de Windows**. Para obtener más información, consulta [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).

## <a name="to-add-and-configure-the-event-log-listener"></a>Para agregar y configurar el agente de escucha de registro de eventos

1. Haga clic con el botón derecho en app.config en el **Explorador de soluciones** y seleccione **Abrir**.

    \- o -

    Si no hay ningún archivo app.config:

    1. En el menú **Proyecto** , elija **Agregar nuevo elemento**.

    2. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.

    3. Haga clic en **Agregar**.

2. Ubique la sección `<listeners>` en el archivo de configuración de la aplicación.

    Encontrará la sección `<listeners>` en la sección `<source>` con el atributo de nombre "DefaultSource", que está anidada bajo la sección `<system.diagnostics>` , anidada bajo la sección de nivel superior `<configuration>` .

3. Agregue este elemento a dicha sección `<listeners>` :

    ```xml
    <add name="EventLog"/>
    ```

4. Busque la sección `<sharedListeners>` , en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .

5. Agregue este elemento a dicha sección `<sharedListeners>` :

    ```xml
    <add name="EventLog"
        type="System.Diagnostics.EventLogTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="APPLICATION_NAME"/>
    ```

    Reemplace `APPLICATION_NAME` por el nombre de su aplicación.

    > [!NOTE]
    > Normalmente, una aplicación escribe solo errores en el registro de eventos. Para obtener información sobre el filtrado de la salida del registro, consulte [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).

## <a name="to-write-event-information-to-the-event-log"></a>Para escribir información de eventos en el registro de eventos

Use el método `My.Application.Log.WriteEntry` o `My.Application.Log.WriteException` para escribir información en el registro de eventos. Para obtener más información, vea [Cómo: Escribir mensajes de registro](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) y [Cómo: Registrar excepciones](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).

Después de configurar el agente de escucha de registro de eventos para un ensamblado, este recibe todos los mensajes que `My.Application.Log` escribe desde ese ensamblado.

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [Registrar excepciones](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [Tutorial: Determinar el lugar en el que My.Application.Log escribe la información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)

---
description: 'Más información acerca de: Procedimiento: para escribir información de eventos en un archivo de texto (Visual Basic)'
title: Procedimiento para escribir información de eventos en un archivo de texto
ms.date: 07/20/2015
helpviewer_keywords:
- event logs [Visual Studio], writing event information
- text files [Visual Basic], writing event information to a text file
- events [Visual Basic], writing event information to a text file
ms.assetid: 9ca7cc03-bf99-4933-9e5e-61ee28e9a6b4
ms.openlocfilehash: eb6fab9976c010080c0cffa37edd4f790dc73956
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99775141"
---
# <a name="how-to-write-event-information-to-a-text-file-visual-basic"></a>Cómo: Escribir información de eventos en un archivo de texto (Visual Basic)

Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre los eventos que se producen en su aplicación. En este ejemplo se muestra cómo usar el método `My.Application.Log.WriteEntry` para registrar información de seguimiento en un archivo de registro.

### <a name="to-add-and-configure-the-file-log-listener"></a>Para agregar y configurar el agente de escucha de registro de archivos

1. Haga clic con el botón derecho en app.config en el **Explorador de soluciones** y seleccione **Abrir**.

     \- o -

     Si no hay ningún archivo app.config:

    1. En el menú **Proyecto** , elija **Agregar nuevo elemento**.

    2. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.

    3. Haga clic en **Agregar**.

2. Ubique la sección `<listeners>` en el archivo de configuración de la aplicación.

     Encontrará la sección \<listeners> en la sección \<source> con el atributo de nombre "DefaultSource", que está anidada bajo la sección \<system.diagnostics> , anidada bajo la sección de nivel superior \<configuration> .

3. Agregue este elemento a dicha sección `<listeners>` :

    ```xml
    <add name="FileLogListener" />
    ```

4. Busque la sección `<sharedListeners>`, en la sección `<system.diagnostics>`, anidada en la sección de nivel superior `<configuration>`.

5. Agregue este elemento a dicha sección `<sharedListeners>` :

    ```xml
    <add name="FileLogListener"
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
              Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,
              PublicKeyToken=b03f5f7f11d50a3a"
        initializeData="FileLogListenerWriter"
        location="Custom"
        customlocation="c:\temp\" />
    ```

     Cambie el valor del atributo `customlocation` al directorio de registro.

    > [!NOTE]
    > Para establecer el valor de una propiedad de agente de escucha, use un atributo que tenga el mismo nombre que la propiedad, con todas las letras del nombre en minúscula. Por ejemplo, los atributos `location` y `customlocation` establecen los valores de las propiedades <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> y <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A>.

### <a name="to-write-event-information-to-the-file-log"></a>Para escribir información de eventos en el registro de archivo

Use el método `My.Application.Log.WriteEntry` o `My.Application.Log.WriteException` para escribir información en el registro de archivo. Para obtener más información, vea [Cómo: Escribir mensajes de registro](how-to-write-log-messages.md) y [Cómo: Registrar excepciones](how-to-log-exceptions.md).

Después de configurar el agente de escucha de registro de archivo para un ensamblado, este recibe todos los mensajes que `My.Application.Log` escribe desde ese ensamblado.

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [Trabajar con registros de aplicaciones](working-with-application-logs.md)
- [Cómo: Registrar excepciones](how-to-log-exceptions.md)

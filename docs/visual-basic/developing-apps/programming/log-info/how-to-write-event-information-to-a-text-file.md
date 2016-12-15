---
title: "C&#243;mo: Escribir informaci&#243;n de eventos en un archivo de texto (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "registro de eventos [Visual Studio], escribir información de eventos"
  - "eventos [Visual Basic], escribir información de eventos en un archivo de texto"
  - "archivos de texto, escribir información de eventos en un archivo de texto"
ms.assetid: 9ca7cc03-bf99-4933-9e5e-61ee28e9a6b4
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Escribir informaci&#243;n de eventos en un archivo de texto (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Puede utilizar los objetos `My.Application.Log` y `My.Log` para registrar información sobre eventos que se producen en la aplicación.  Este ejemplo muestra cómo utilizar el método `My.Application.Log.WriteEntry` para registrar información de traza en un archivo de registro.  
  
### Para agregar y configurar el agente de escucha del registro de archivos  
  
1.  Haga clic con el botón secundario en app.config en el **Explorador de soluciones** y elija **Abrir**.  
  
     \-O bien\-  
  
     Si no hay un archivo app.config:  
  
    1.  En el menú **Proyecto**, elija **Agregar nuevo elemento**.  
  
    2.  En el cuadro de diálogo **Agregar nuevo elemento**, elija **Archivo de configuración de aplicaciones**.  
  
    3.  Haga clic en **Agregar**.  
  
2.  Busque la sección `<listeners>` en el archivo de configuración de la aplicación.  
  
     Encontrará la sección \<listeners\> en la sección \<source\> con el atributo de nombre "DefaultSource", anidada en la sección \<system.diagnostics\>, anidada a su vez en la sección de nivel superior \<configuration\>.  
  
3.  Agregue este elemento a esa sección `<listeners>`:  
  
    ```  
    <add name="FileLogListener" />  
    ```  
  
4.  Busque la sección `<sharedListeners>` en la sección `<system.diagnostics>`, anidada bajo la sección de nivel superior `<configuration>`.  
  
5.  Agregue este elemento a esa sección `<sharedListeners>`:  
  
    ```  
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
    >  Para establecer el valor de una propiedad de agente de escucha, utilice un atributo con el mismo nombre que la propiedad, con todas las letras del nombre en minúscula.  Por ejemplo, los atributos `location` y `customlocation` establecen los valores de las propiedades <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> y <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A>.  
  
### Para escribir información de evento en el registro de archivos  
  
-   Utilice el método `My.Application.Log.WriteEntry` o `My.Application.Log.WriteException` para escribir información en el registro de archivos.  Para obtener más información, vea [Cómo: Escribir mensajes de registro](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) y [Cómo: Registrar excepciones](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).  
  
     Después de configurar el agente de escucha del registro de archivos para un ensamblado, el agente recibe todos los mensajes que `My.Application.Log` escribe desde dicho ensamblado.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>   
 [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Cómo: Registrar excepciones](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
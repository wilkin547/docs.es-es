---
title: "Tutorial: Crear agentes de escucha de registro personalizados (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "agentes de escucha de registro predeterminados"
  - "My.Application.Log (objeto), agentes de escucha de registro predeterminados"
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Tutorial: Crear agentes de escucha de registro personalizados (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Este tutorial muestra cómo crear un agente de escucha de registro personalizado y configurarlo para esperar el resultado del objeto `My.Application.Log`.  
  
## Introducción  
 Los agentes de escucha de registro deben heredar de la clase <xref:System.Diagnostics.TraceListener>.  
  
#### Para crear el agente de escucha  
  
-   En su aplicación, cree una clase denominada `SimpleListener` que herede de <xref:System.Diagnostics.TraceListener>.  
  
     [!code-vb[VbVbalrMyApplicationLog#16](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_1.vb)]  
  
     Los métodos <xref:System.Diagnostics.TraceListener.Write%2A> y <xref:System.Diagnostics.TraceListener.WriteLine%2A>, requeridos por la clase base, llaman a `MsgBox` para mostrar su entrada.  
  
     El atributo <xref:System.Security.Permissions.HostProtectionAttribute> se aplica a los métodos <xref:System.Diagnostics.TraceListener.Write%2A> y <xref:System.Diagnostics.TraceListener.WriteLine%2A> para que sus atributos coincidan con los métodos de la clase base.  El atributo <xref:System.Security.Permissions.HostProtectionAttribute> permite al host que ejecuta el código determinar que el código expone sincronización de protección del host.  
  
    > [!NOTE]
    >  El atributo <xref:System.Security.Permissions.HostProtectionAttribute> sólo es eficaz en aplicaciones no administradas que hospedan Common Language Runtime e implementan esa protección de host, como SQL Server.  
  
 Para garantizar que `My.Application.Log` utiliza su agente de escucha de registro, debería utilizar un nombre seguro para el ensamblado que contiene su agente de escucha de registro.  
  
 El procedimiento siguiente proporciona algunos pasos simples para crear un ensamblado de agente de escucha de registro con nombre seguro.  Para obtener más información, vea [Crear y utilizar ensamblados con nombre seguro](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md).  
  
#### Para asignar un nombre seguro al ensamblado de agente de escucha de registro  
  
1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, elija **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Haga clic en la ficha **Firma**.  
  
3.  Active la casilla **Firmar el ensamblado**.  
  
4.  Seleccione **\<Nuevo\>** en la lista desplegable **Elija un archivo de clave de nombre seguro**.  
  
     Aparecerá el cuadro de diálogo **Crear clave de nombre seguro**.  
  
5.  Proporcione un nombre para el archivo de clave en el cuadro **Nombre del archivo de clave**.  
  
6.  Escriba una contraseña en los cuadros **Escribir contraseña** y **Confirmar contraseña**.  
  
7.  Haga clic en **Aceptar**.  
  
8.  Recompile la aplicación.  
  
## Agregar el agente de escucha  
 Ahora que el ensamblado tiene un nombre seguro, es necesario determinar el nombre seguro del agente de escucha para que `My.Application.Log` utilice su agente de escucha de registro.  
  
 El formato de un tipo con nombre seguro es como sigue.  
  
 \<nombre de tipo\>, \<nombre de ensamblado\>, \<número de versión\>, \<referencia cultural\>, \<nombre seguro\>  
  
#### Para determinar el nombre seguro del agente de escucha  
  
-   El código siguiente muestra cómo determinar el nombre seguro del tipo de `SimpleListener`.  
  
     [!code-vb[VbVbalrMyApplicationLog#17](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_2.vb)]  
  
     El nombre seguro del tipo depende de su proyecto.  
  
 Con el nombre seguro, puede agregar el agente de escucha a la colección del agente de escucha de registro de `My.Application.Log`.  
  
#### Para agregar el agente de escucha a My.Application.Log  
  
1.  Haga clic con el botón secundario del mouse en app.config en el **Explorador de soluciones** y elija **Abrir**.  
  
     O bien  
  
     Si hay un archivo app.config:  
  
    1.  En el menú **Proyecto**, elija **Agregar nuevo elemento**.  
  
    2.  En el cuadro de diálogo **Agregar nuevo elemento**, elija **Archivo de configuración de aplicaciones**.  
  
    3.  Haga clic en **Agregar**.  
  
2.  Busque la sección `<listeners>`, dentro de la sección `<source>` que tiene el atributo `name` "DefaultSource", situado en la sección `<sources>`.  La sección `<sources>` se encuentra dentro de la sección `<system.diagnostics>`, en la sección de nivel superior `<configuration>`.  
  
3.  Agregue este elemento a la sección `<listeners>`:  
  
    ```  
    <add name="SimpleLog" />  
    ```  
  
4.  Busque la sección `<sharedListeners>`, en la sección `<system.diagnostics>`, de la sección `<configuration>` de nivel superior.  
  
5.  Agregue este elemento a esa sección `<sharedListeners>`:  
  
    ```  
    <add name="SimpleLog" type="SimpleLogStrongName" />  
    ```  
  
     Cambie el valor de `SimpleLogStrongName` para que sea el nombre seguro del agente de escucha.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Cómo: Registrar excepciones](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)   
 [Cómo: Escribir mensajes de registro](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [Tutorial: Cambiar el lugar donde My.Application.Log escribe información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
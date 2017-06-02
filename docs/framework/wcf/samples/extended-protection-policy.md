---
title: "Directiva de protecci&#243;n extendida | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e2616a10-317e-4c34-8023-0c015a80a82f
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Directiva de protecci&#243;n extendida
Protección extendida es una iniciativa de seguridad para protegerse contra los ataques de tipo "Man in the middle" \(MITM\).  Un ataque MITM es una amenaza de seguridad en la que MITM toma las credenciales de un cliente y lo reenvía a un servidor.  
  
## Demostraciones  
 Protección extendida  
  
## Explicación  
 Cuando las aplicaciones cliente se autentican mediante Kerberos, Digest o NTLM usando HTTPS, se establece en primer lugar un canal de Seguridad de nivel de transporte \(TLS\) y después la autenticación se lleva a cabo usando el canal seguro.  Sin embargo, no hay ningún enlace entre la clave de sesión generada por SSL y la clave de sesión generada durante la autenticación.  MITM se puede establecer entre el cliente y el servidor, y comienza a reenviar las solicitudes del cliente, incluso cuando el propio canal de transporte es seguro, porque el servidor no tiene ninguna manera de saber si el canal seguro se ha establecido desde el cliente o desde un MITM.  La solución en este escenario es enlazar el canal de TLS externo con el canal de autenticación interno de modo que el servidor puede detectar si hay un MITM.  
  
> [!NOTE]
>  Este ejemplo solo funciona cuando se hospeda en IIS y no puede trabajar en Cassini. El servidor de desarrollo de Visual Studio porque Cassini no admite HTTPS.  
  
> [!NOTE]
>  Esta característica solo está disponible actualmente en Windows 7.  Los siguientes pasos son específicos de Windows 7.  
  
#### Configurar, compilar y ejecutar el ejemplo  
  
1.  Instale Internet Information Services desde el **Panel de control**, **Agregar o quitar programas**, **Características de Windows**.  
  
2.  Instale la **Autenticación de Windows** en **Características de Windows**, **Internet Information Services**, **Servicios World Wide Web**, **Seguridad** y **Autenticación de Windows**.  
  
3.  Instale **Activación HTTP de Windows Communication Foundation** en **Características de Windows**, **Microsoft .NET Framework 3.5.1** y **Activación HTTP de Windows Communication Foundation**.  
  
4.  Este ejemplo requiere que el cliente establezca un canal seguro con el servidor, por lo que es necesaria la presencia de un certificado de servidor que se puede instalar desde el Administrador de Internet Information Services \(IIS\).  
  
    1.  Abra el Administrador de IIS.  Abra **Certificados de servidor**, que aparecen en la pestaña **Vista de características** cuando el nodo raíz \(nombre de equipo\) está seleccionado.  
  
    2.  Para las pruebas de este ejemplo, puede crear un certificado autofirmado.  Si no desea que Internet Explorer le indique que el certificado no es seguro, instálelo en el almacén Entidades emisoras de certificados raíz de confianza.  
  
5.  Abra el panel **Acciones** del sitio web predeterminado.  Haga clic en **Modificar sitio** y en **Enlaces**.  Agregue HTTPS como un tipo si no está presente, con el número de puerto 443.  Asigne el certificado SSL creado en el paso anterior.  
  
6.  Compile el servicio.  De esta forma se crea un directorio virtual en IIS y se copian los archivos .dll, .svc y .config, tal y como se requiere para que el servicio se hospede en web.  
  
7.  Abra el Administrador de IIS.  Haga clic con el botón secundario en el directorio virtual \(**ExtendedProtection**\), que se creó en el paso anterior.  Seleccione **Convertir en aplicación**.  
  
8.  Abra el módulo **Autenticación** en el Administrador de IIS para este directorio virtual y habilite **Autenticación de Windows**.  
  
9. Abra **Configuración avanzada**, en **Autenticación de Windows**, para este directorio virtual y establézcalo en **Requerido**.  
  
10. Puede probar el servicio teniendo acceso a la dirección URL HTTPS de una ventana del explorador \(proporcione un nombre de dominio completo\).  Si desea tener acceso a esta dirección URL desde un equipo remoto, asegúrese de que el firewall está abierto para todas las conexiones HTTP y HTTPS entrantes.  
  
11. Abra el archivo de configuración del cliente y proporcione un nombre de dominio completo para el cliente o el atributo de dirección de extremo que reemplace a `<<full_machine_name>>`.  
  
12. Ejecute el cliente.  El cliente se comunica con el servicio, que establece un canal seguro y utiliza la protección extendida.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.  Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Security\ExtendedProtection`
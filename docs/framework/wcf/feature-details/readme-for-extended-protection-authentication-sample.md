---
title: "Archivo ReadMe del ejemplo de protecci&#243;n extendida para la autenticaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
caps.latest.revision: 3
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 3
---
# Archivo ReadMe del ejemplo de protecci&#243;n extendida para la autenticaci&#243;n
La protección extendida es una iniciativa de seguridad para protegerse de ataques de tipo "man\-in\-the\-middle" \(MITM\), en los que un atacante \(“man\-in\-the\-middle”\) intercepta las credenciales de un cliente y las usa para obtener acceso a recursos seguros en el servidor de destino del cliente.  
  
 Para obtener más información, vea [Información general sobre la protección extendida para la autenticación](../../../../docs/framework/wcf/feature-details/extended-protection-for-authentication-overview.md).  
  
> [!NOTE]
>  Esta muestra solo funciona cuando se hospeda en IIS.No funciona en el servidor de desarrollo de Visual Studio, ya que este no admite HTTPS.  
  
## Para configurar, compilar y ejecutar el ejemplo  
  
1.  Instale IIS en el equipo mediante Agregar o quitar programas \-\> Características de Windows.  
  
2.  Active la autenticación de Windows en las características de Windows: Internet Information Services \-\> Servicios World Wide Web \-\> Seguridad \-\> Autenticación de Windows.  
  
3.  Active la activación HTTP en las características de Windows: Microsoft .NET Framework 3.5.1 \-\> Activación HTTP de Windows Communication Foundation.  
  
4.  Este ejemplo requiere que el cliente establezca un canal seguro con el servidor, por lo que es necesaria la presencia de un certificado de servidor que se puede instalar desde el Administrador de Internet Information Services \(IIS\).  
  
    1.  Abra el Administrador de IIS \-\> Certificados de servidor \(en la pestaña de vista de características\).  
  
    2.  Con fines de prueba de esta muestra, puede crear un certificado autofirmado.\(Si no desea que Internet Explorer le indique que el certificado no es seguro, puede instalarlo en el almacén Entidades emisoras de certificados raíz de confianza\).  
  
5.  Vaya al panel Acciones del sitio web predeterminado.Haga clic en Modificar sitio \-\> Enlaces.Agregue HTTPS como tipo si aún no está presente, con el número de puerto 443, y asigne el certificado SSL creado en el paso anterior.  
  
6.  Compile el servicio.Esto crea un directorio virtual en IIS \(a partir de la acción posterior a la compilación especificada en las propiedades del proyecto\) y copia los archivos dll, .svc y config según sea necesario para que un servicio se hospede en web.  
  
7.  Abra el Administrador de IIS.Haga clic con el botón secundario en el directorio virtual \(ExtendedProtection\) que creó en el paso anterior y seleccione Convertir en aplicación.  
  
8.  Abra el módulo de autenticación en el Administrador de IIS para este directorio virtual y habilite la autenticación de Windows.  
  
9. Abra la Configuración avanzada de la autenticación de Windows para este directorio virtual y establézcala en Requerida, ya que en el ejemplo el valor ExtendedProtection correspondiente está establecido en Siempre.  
  
10. Puede probar el servicio obteniendo acceso a la dirección URL desde una ventana del explorador.Si desea tener acceso a esta dirección URL desde varios equipos, asegúrese de que el firewall está abierto para todas las conexiones HTTP y HTTPS entrantes.  
  
11. Abra el archivo de configuración del cliente y proporcione un nombre completo de equipo para \<client\> \- \<endpoint\> \- address attribute, que reemplace a \<\<full\_machine\_name\>\>.  
  
12. Ejecute el cliente.El cliente se comunica con el servicio estableciendo un canal seguro y usando la protección extendida.
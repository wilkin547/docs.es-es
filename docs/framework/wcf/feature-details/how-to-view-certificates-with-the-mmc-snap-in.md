---
title: "C&#243;mo: Ver certificados con el complemento de MMC | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "certificados [WCF], visualización con el complemento de MMC"
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# C&#243;mo: Ver certificados con el complemento de MMC
Un tipo común de credencial es el certificado X.509.Al crear servicios o clientes seguros, puede especificar que un certificado se utilice como la credencial del cliente o servicio utilizando métodos como el método <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>.El método requiere varios parámetros, como el almacén donde se guarda el certificado y un valor que utilizar al buscar el certificado.El siguiente procedimiento muestra cómo examinar los almacenes de un equipo para encontrar un certificado adecuado.Para obtener un ejemplo de cómo encontrar la huella digital del certificado, vea [Cómo recuperar la huella digital de un certificado](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
### Para ver los certificados en el complemento de MMC  
  
1.  Abra una ventana de símbolo del sistema.  
  
2.  Escriba `mmc` y, a continuación, pulse la tecla ENTER.Tenga en cuenta que para ver los certificados en el almacén del equipo local, debe estar en la función del Administrador.  
  
3.  En el menú **Archivo**, haga clic en **Agregar o quitar complemento**.  
  
4.  Haga clic en **Agregar**.  
  
5.  En el cuadro de diálogo **Agregar un complemento independiente**, seleccione **Certificados**.  
  
6.  Haga clic en **Agregar**.  
  
7.  En el cuadro de diálogo **Complemento Certificados**, seleccione **Cuenta de equipo** y haga clic en **Siguiente**.Opcionalmente, puede seleccionar **Mi cuenta de usuario** o **Cuenta de servicio**.Si no es ningún administrador del equipo, solo puede administrar los certificados para su cuenta de usuario.  
  
8.  En el cuadro de diálogo **Seleccionar equipo**, haga clic en **Finalizar**.  
  
9. En el cuadro de diálogo **Agregar un complemento independiente**, haga clic en **Cerrar**.  
  
10. En el cuadro de diálogo **Agregar o quitar complemento**, haga clic en **Aceptar**.  
  
11. En la ventana **Raíz de consola**, haga clic en **Certificados \(Equipo local\)** para ver los almacenes de certificados para el equipo.  
  
12. Opcional.Para ver los certificados para su cuenta, repita los pasos 3 a 6.En el paso 7, en lugar de seleccionar **Cuenta de equipo**, haga clic en **Mi cuenta de usuario** y repita los pasos del 8 al 10.  
  
13. Opcional.En el menú **Archivo**, haga clic en **Guardar** o **Guardar como**.Guarde el archivo de consola para utilizarlo más adelante.  
  
## Ver certificados con Internet Explorer  
 También puede ver, exportar, importar y eliminar certificados utilizando Internet Explorer.  
  
#### Para ver certificados con Internet Explorer  
  
1.  En Internet Explorer, haga clic en **Herramientas** y, a continuación, haga clic en **Opciones de Internet** para mostrar el cuadro de diálogo **Opciones de Internet**.  
  
2.  Haga clic en la pestaña **Contenido**.  
  
3.  En **Certificados**, haga clic en **Certificados**.  
  
4.  Para ver detalles de cualquier certificado, seleccione el certificado y haga clic en **Ver**.  
  
## Vea también  
 [Trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Cómo: Crear certificados temporales que puedan utilizarse durante las operaciones de desarrollo](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)   
 [Cómo recuperar la huella digital de un certificado](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
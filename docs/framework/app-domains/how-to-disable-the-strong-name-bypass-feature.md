---
title: "C&#243;mo: Deshabilitar la caracter&#237;stica de omisi&#243;n de nombres seguros | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "característica de omisión de nombres seguros"
  - "ensamblados con nombre seguro, cargar en dominios de aplicación de confianza"
ms.assetid: 234e088c-3b11-495a-8817-e0962be79d82
caps.latest.revision: 30
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 30
---
# C&#243;mo: Deshabilitar la caracter&#237;stica de omisi&#243;n de nombres seguros
A partir de .NET Framework versión 3.5 Service Pack 1 \(SP1\), las firmas con nombre seguro no se validan cuando un ensamblado se carga en un objeto <xref:System.AppDomain> de plena confianza, como el objeto <xref:System.AppDomain> predeterminado de la zona `MyComputer`.  Esto es lo que se denomina característica de omisión de nombres seguros.  En un entorno de plena confianza, las peticiones de <xref:System.Security.Permissions.StrongNameIdentityPermission> siempre se realizan correctamente en los ensamblados firmados de plena confianza independientemente de su firma.  La única restricción es que el ensamblado debe ser de plena confianza porque su zona es de plena confianza.  Dado que el nombre seguro no constituye un factor determinante en estas circunstancias, no hay ninguna razón para que se valide.  Al omitir la validación de las firmas con nombre seguro, mejora considerablemente en rendimiento.  
  
 La característica de omisión se aplica a cualquier ensamblado de plena confianza que no sea de firma retardada de cualquier objeto <xref:System.AppDomain> de plena confianza del directorio especificado por su propiedad <xref:System.AppDomainSetup.ApplicationBase%2A>.  
  
 Puede invalidar la característica de omisión en todas las aplicaciones de un equipo a través de un valor de clave del Registro.  Puede invalidar el valor en una única aplicación a través de un archivo de configuración de la aplicación.  No puede restablecer la característica de omisión de una única aplicación si se deshabilitó mediante la clave del Registro.  
  
 Al invalidar la característica de omisión, el nombre seguro se valida únicamente para garantizar que todo es correcto; no se comprueba a efectos del permiso <xref:System.Security.Permissions.StrongNameIdentityPermission>.  Si desea confirmar un nombre seguro concreto, deberá realizar esa comprobación por separado.  
  
> [!IMPORTANT]
>  La capacidad de forzar la validación de nombres seguros depende de una clave del Registro, tal y como se describe en el procedimiento siguiente.  Si una aplicación se está ejecutando bajo una cuenta que no tiene el permiso de lista de control de acceso \(ACL\) para obtener acceso a esa clave del Registro, el valor no tiene efecto.  Debe asegurarse de que se configuren los derechos ACL para esta clave de manera que pueda ser leída para todos los ensamblados.  
  
### Para deshabilitar la característica de omisión de nombres seguros en todas las aplicaciones  
  
-   En equipos de 32 bits, en el Registro del sistema, cree una entrada DWORD con un valor de 0 denominado `AllowStrongNameBypass` bajo la clave HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework.  
  
-   En equipos de 64 bits, en el Registro del sistema, cree una entrada DWORD con un valor de 0 denominado `AllowStrongNameBypass` en las claves HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework y HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\.NETFramework.  
  
### Para deshabilitar la característica de omisión de nombres seguros en una única aplicación  
  
1.  Abra o cree el archivo de configuración de la aplicación.  
  
     Para obtener más información sobre este archivo, vea la sección Archivos de configuración de la aplicación en [Configurar aplicaciones](../../../docs/framework/configure-apps/index.md).  
  
2.  Agregue la entrada siguiente:  
  
    ```  
    <configuration>  
      <runtime>  
         < bypassTrustedAppStrongNames enabled="false" />  
      </runtime>  
    </configuration>  
    ```  
  
 Para restaurar la característica de omisión en la aplicación, quite el valor del archivo de configuración o establezca el atributo en "true".  
  
> [!NOTE]
>  Solo puede activar y desactivar la validación de nombres seguros en una aplicación si la característica de omisión está habilitada en el equipo.  Si la característica de omisión se deshabilitó en el equipo, los nombres seguros se validan en todas las aplicaciones y no se puede omitir la validación en una única aplicación.  
  
## Vea también  
 [Sn.exe \(Strong Name Tool\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)   
 [Elemento \<bypassTrustedAppStrongNames\>](../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)   
 [Crear y utilizar ensamblados con nombre seguro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
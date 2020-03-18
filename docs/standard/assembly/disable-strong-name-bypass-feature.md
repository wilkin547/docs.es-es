---
title: Procedimiento para deshabilitar la característica de omisión de nombres seguros
ms.date: 08/20/2019
helpviewer_keywords:
- strong-name bypass feature
- strong-named assemblies, loading into trusted application domains
ms.assetid: 234e088c-3b11-495a-8817-e0962be79d82
ms.openlocfilehash: a4c4ae7ea61a659d3bede532da3c1bdaea448873
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141100"
---
# <a name="how-to-disable-the-strong-name-bypass-feature"></a>Procedimiento para deshabilitar la característica de omisión de nombres seguros
A partir de .NET Framework versión 3.5 Service Pack 1 (SP1), las firmas de nombre seguro no se validan cuando un ensamblado se carga en un objeto <xref:System.AppDomain> de plena confianza, como el objeto <xref:System.AppDomain> predeterminado para la zona `MyComputer`. Esta característica se denomina omisión de nombres seguros. En un entorno de plena confianza, las peticiones de <xref:System.Security.Permissions.StrongNameIdentityPermission> siempre se realizan correctamente para los ensamblados de plena confianza firmados, independientemente de su firma. La única restricción es que el ensamblado debe ser de plena confianza porque su zona es de plena confianza. Dado que el nombre seguro no es un factor determinante en estas condiciones, no hay ninguna razón para que se valide. La omisión de la validación de firmas de nombre seguro proporciona importantes mejoras en el rendimiento.  
  
 La característica de omisión se aplica a todos los ensamblados de plena confianza que no tienen firma retrasada y que se cargan en un objeto <xref:System.AppDomain> de plena confianza desde el directorio especificado por la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A>.  
  
 Puede invalidar la característica de omisión para todas las aplicaciones de un equipo. Para ello, establezca un valor de clave del Registro. Puede invalidar la configuración de una aplicación mediante un archivo de configuración de la aplicación. No se puede restablecer la característica de omisión de una sola aplicación si se ha deshabilitado mediante la clave del Registro.  
  
 Cuando se invalida la característica de omisión, el nombre seguro se valida únicamente para comprobar que es correcto; no se comprueba su <xref:System.Security.Permissions.StrongNameIdentityPermission>. Si quiere confirmar un nombre seguro específico, tendrá que hacerlo por separado.  
  
> [!IMPORTANT]
> La capacidad de forzar la validación del nombre seguro depende de una clave del Registro, como se indica en el procedimiento siguiente. Si una aplicación se ejecuta en una cuenta que no tiene permiso de lista de control de acceso (ACL) para tener acceso a esa clave del Registro, el valor no tiene efecto. Debe asegurarse de que se han configurado permisos de ACL para esta clave de modo que se pueda leer para todos los ensamblados.  
  
## <a name="disable-the-strong-name-bypass-feature-for-all-applications"></a>Cómo deshabilitar la característica de omisión de nombres seguros para todas las aplicaciones  
  
- En equipos de 32 bits, en el Registro del sistema, cree una entrada DWORD con un valor de 0 denominada `AllowStrongNameBypass` en la clave HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework.  
  
- En equipos de 64 bits, en el Registro del sistema, cree una entrada DWORD con un valor de 0 denominada `AllowStrongNameBypass` en las claves HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework y HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework.  
  
## <a name="disable-the-strong-name-bypass-feature-for-a-single-application"></a>Cómo deshabilitar la característica de omisión de nombres seguros para una sola aplicación  
  
1. Abra o cree el archivo de configuración de la aplicación.  
  
    Para obtener más información sobre este archivo, vea la sección sobre archivos de configuración de la aplicación en [Configuración de aplicaciones](../../framework/configure-apps/index.md).  
  
2. Agregue la siguiente entrada:  
  
    ```xml  
    <configuration>  
      <runtime>  
        <bypassTrustedAppStrongNames enabled="false" />  
      </runtime>  
    </configuration>  
    ```  
  
 Puede restaurar la característica de omisión de la aplicación. Para ello, elimine el valor del archivo de configuración o establezca el atributo en `true`.  
  
> [!NOTE]
> Puede activar y desactivar la validación del nombre seguro de una aplicación únicamente si la característica de omisión está habilitada para el equipo. Si la característica de omisión se ha desactivado para el equipo, los nombres seguros se validan para todas las aplicaciones y no se puede omitir la validación de una sola aplicación.  
  
## <a name="see-also"></a>Vea también

- [Sn.exe (Herramienta de nombre seguro)](../../framework/tools/sn-exe-strong-name-tool.md)
- Elemento [\<bypassTrustedAppStrongNames>](../../framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)
- [Creación y uso de ensamblados con nombre seguro](create-use-strong-named.md)

---
title: Configurar la redirección del enlace de ensamblados
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: d266cbd8-bf91-41d1-baf0-afbc481a741f
ms.openlocfilehash: c7b9dcb99e08a1ef2844c5811897aa87ff86f866
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716554"
---
# <a name="configuring-assembly-binding-redirection"></a>Configurar la redirección del enlace de ensamblados
De forma predeterminada, las aplicaciones usan los ensamblados de .NET Framework que se incluyen con la versión del tiempo de ejecución usada para compilar la aplicación. Puede usar el atributo **appliesTo** en el elemento [\<assemblyBinding>](../configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) de un archivo de configuración de la aplicación para redirigir las referencias de enlace de ensamblados a una versión específica de los ensamblados de .NET Framework. Este atributo opcional usa un número de versión de .NET Framework para indicar a qué versión se aplica. Si no se especifica ningún atributo **appliesTo**, el elemento **\<assemblyBinding>** se aplica a todas las versiones de .NET Framework.  
  
 El atributo **appliesTo** se incorporó en la versión 1.1 de .NET Framework; se pasa por alto en la versión 1.0 de .NET Framework. Esto significa que se aplican todos los elementos **\<assemblyBinding>** cuando se usa la versión 1.0 de .NET Framework, aunque se especifique un atributo **appliesTo**.  
  
> [!NOTE]
> Use el atributo **appliesTo** para limitar la redirección de enlace de ensamblados a una versión específica del tiempo de ejecución.  
  
 Por ejemplo, para redirigir el enlace de un ensamblado de la versión 1.0 de .NET Framework, incluiría el siguiente código XML en el archivo de configuración de la aplicación.  
  
```xml  
<runtime>  
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
            <dependentAssembly>   
               * assembly information goes here *  
            </dependentAssembly>  
       </assemblyBinding>  
</runtime>  
```  
  
 Los elementos **\<assemblyBinding>** tienen en cuenta el orden. Primero debe especificar la información de redirección de enlace de los ensamblados de la versión 1.0 de .NET Framework, seguida de la información de redirección de enlace de los ensamblados de la versión 1.1 de .NET Framework. Por último, especifique la información de redirección de enlace de ensamblados para cualquier redirección de ensamblados de .NET Framework que no use el atributo **appliesTo** y, por tanto, se aplica a todas las versiones de .NET Framework. En el caso de un conflicto en la redirección, se usa la primera instrucción de redirección que coincida en el archivo de configuración.  
  
 Por ejemplo, para redirigir una referencia a un ensamblado de la versión 1.0 de .NET Framework y otra referencia a un ensamblado de la versión 1.1 de .NET Framework, usaría el patrón que se muestra en el siguiente pseudocódigo.  
  
```xml  
<assemblyBinding xmlns="..." appliesTo="v1.0.3705">   
  <!-- .NET Framework version 1.0 redirects here. -->   
</assemblyBinding>   
  
<assemblyBinding xmlns="..." appliesTo="v1.1.4322">   
  <!-- .NET Framework version 1.1 redirects here. -->   
</assemblyBinding>   
  
<assemblyBinding xmlns="...">   
  <!-- Redirects meant for all versions of the .NET Framework. -->   
</assemblyBinding>  
```  
  
## <a name="debugging-configuration-file-errors"></a>Depurar errores de archivos de configuración  
 El tiempo de ejecución analiza los archivos de configuración una vez cuando se crea un dominio de aplicación y carga el código en ese dominio de aplicación. Common Language Runtime controla los errores en un archivo de configuración omitiendo la entrada. El tiempo de ejecución omite el archivo de configuración completo si contiene código XML con formato incorrecto. En el caso de código XML no válido, se omiten solo las secciones no válidas.  
  
 Para determinar si un archivo de configuración se está usando, determine si se producen redirecciones de enlace de ensamblados. Use el [Visor de registro de enlaces de ensamblados (Fuslogvw.exe)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) para ver qué ensamblados se van a cargar. Para ver todos los enlaces de ensamblado, debe establecer una entrada para **ForceLog** en el Registro.  
  
## <a name="see-also"></a>Vea también

- [Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)

---
title: <loadFromRemoteSources> (Elemento)
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8e8663bf9d119007eb7d3771d16d55b1aa54856
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663607"
---
# <a name="loadfromremotesources-element"></a>\<loadFromRemoteSources >, elemento
Especifica si se debe conceder plena confianza a los ensamblados cargados desde orígenes remotos en .NET Framework 4 y versiones posteriores.
  
> [!NOTE]
>  Si se le dirigió a este artículo debido a un mensaje de error en la lista de errores del proyecto de Visual Studio o un [error de compilación, consulte Cómo: Usar un ensamblado desde la web en Visual](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100))Studio.  
  
 \<configuration>  
\<> en tiempo de ejecución  
\<loadFromRemoteSources>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si se debe conceder plena confianza a un ensamblado que se carga desde un origen remoto.|  
  
## <a name="enabled-attribute"></a>atributo Enabled  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|`false`|No conceda plena confianza a las aplicaciones de orígenes remotos. Este es el valor predeterminado.|  
|`true`|Conceda plena confianza a las aplicaciones desde orígenes remotos.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios

En el .NET Framework 3,5 y versiones anteriores, si carga un ensamblado desde una ubicación remota, el código del ensamblado se ejecuta en confianza parcial con un conjunto de permisos concedidos que depende de la zona desde la que se carga. Por ejemplo, si carga un ensamblado desde un sitio web, se carga en la zona de Internet y se le concede el conjunto de permisos de Internet. En otras palabras, se ejecuta en un espacio aislado de Internet.

A partir de la .NET Framework 4, la Directiva de seguridad de acceso del código (CAS) está deshabilitada y los ensamblados se cargan con plena confianza. Normalmente, esto concedería plena confianza a los ensamblados cargados <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> con el método que anteriormente tenía un espacio aislado. Para evitar esto, la capacidad de ejecutar código en los ensamblados cargados desde un origen remoto está deshabilitada de forma predeterminada. De forma predeterminada, si intenta cargar un ensamblado remoto, se <xref:System.IO.FileLoadException> produce una con un mensaje de excepción similar al siguiente:

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

Para cargar el ensamblado y ejecutar su código, debe:

- Cree explícitamente un espacio aislado para el ensamblado (vea [cómo: Ejecutar código de confianza parcial en un](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)espacio aislado).

- Ejecute el código del ensamblado con plena confianza. Para ello, configure el `<loadFromRemoteSources>` elemento. Le permite especificar que los ensamblados que se ejecutan en confianza parcial en versiones anteriores del .NET Framework ahora se ejecutan en plena confianza en el .NET Framework 4 y versiones posteriores.

> [!IMPORTANT]
> Si el ensamblado no debe ejecutarse con plena confianza, no establezca este elemento de configuración. <xref:System.AppDomain> En su lugar, cree un espacio aislado en el que cargar el ensamblado.

El `enabled` atributo del `<loadFromRemoteSources>` elemento solo es efectivo cuando está deshabilitada la seguridad de acceso del código (CAS). De forma predeterminada, la Directiva CAS está deshabilitada en el .NET Framework 4 y versiones posteriores. Si establece `enabled` en, `true`se concederá plena confianza a los ensamblados remotos.

Si `enabled` no se establece en `true`, se <xref:System.IO.FileLoadException> produce una excepción en cualquiera de las siguientes condiciones:

- El comportamiento de espacio aislado del dominio actual es diferente de su comportamiento en el .NET Framework 3,5. Esto requiere que la Directiva de CAS esté deshabilitada y que el dominio actual no esté en un espacio aislado.

- El ensamblado que se está cargando no `MyComputer` es de la zona.

Establecer el `<loadFromRemoteSources>` elemento en `true` evita que se produzca esta excepción. Permite especificar que no se confíe en el Common Language Runtime para crear un espacio aislado de seguridad de los ensamblados cargados y que se puedan ejecutar con plena confianza.

## <a name="notes"></a>Notas

- En el .NET Framework 4,5 y versiones posteriores, los ensamblados de recursos compartidos de red locales se ejecutan de forma predeterminada en plena confianza. no es necesario habilitar el `<loadFromRemoteSources>` elemento.

- Si se ha copiado una aplicación de la web, Windows la marca como una aplicación Web, aunque se encuentre en el equipo local. Puede cambiar esa designación cambiando sus propiedades de archivo, o puede usar el `<loadFromRemoteSources>` elemento para conceder plena confianza al ensamblado. Como alternativa, puede utilizar el <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> método para cargar un ensamblado local que el sistema operativo ha marcado como cargado desde Internet.

- Puede obtener un <xref:System.IO.FileLoadException> en una aplicación que se ejecuta en una aplicación de Windows Virtual PC. Esto puede ocurrir cuando se intenta cargar un archivo desde carpetas vinculadas en el equipo host. También se puede producir al intentar cargar un archivo desde una carpeta vinculada a través de [servicios de escritorio remoto](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services). Para evitar la excepción, establezca `enabled` en `true`.

## <a name="configuration-file"></a>Archivo de configuración

Este elemento se utiliza normalmente en el archivo de configuración de la aplicación, pero se puede usar en otros archivos de configuración en función del contexto. Para obtener más información, vea el artículo [uso más implícito de la Directiva CAS: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) en el blog de seguridad de .net.  

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo conceder plena confianza a los ensamblados cargados desde orígenes remotos.

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a>Vea también

- [Usos más implícitos de la Directiva CAS: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839)
- [Procedimientos: Ejecutar código de confianza parcial en un espacio aislado](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

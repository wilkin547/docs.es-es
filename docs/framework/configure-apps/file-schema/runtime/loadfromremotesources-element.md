---
title: <loadFromRemoteSources> (Elemento)
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154067"
---
# <a name="loadfromremotesources-element"></a>\<elemento> loadFromRemoteSources
Especifica si los ensamblados cargados desde orígenes remotos deben tener plena confianza en .NET Framework 4 y versiones posteriores.
  
> [!NOTE]
> Si se le dirigió a este artículo debido a un mensaje de error en la lista de errores del proyecto de Visual Studio o un error de compilación, vea [Cómo: usar un ensamblado desde la Web en Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si se debe conceder plena confianza a un ensamblado que se carga desde un origen remoto.|  
  
## <a name="enabled-attribute"></a>atributo habilitado  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|No conceda plena confianza a las aplicaciones de orígenes remotos. Este es el valor predeterminado.|  
|`true`|Conceda plena confianza a las aplicaciones de fuentes remotas.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Observaciones

En .NET Framework 3.5 y versiones anteriores, si carga un ensamblado desde una ubicación remota, el código del ensamblado se ejecuta en confianza parcial con un conjunto de subvenciones que depende de la zona desde la que se carga. Por ejemplo, si carga un ensamblado desde un sitio web, se carga en la zona de Internet y se le concede el conjunto de permisos de Internet. En otras palabras, se ejecuta en un entorno limitado de Internet.

A partir de .NET Framework 4, la directiva de seguridad de acceso al código (CAS) está deshabilitada y los ensamblados se cargan con plena confianza. Normalmente, esto concedería plena confianza a los <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> ensamblados cargados con el método que anteriormente se había aislado. Para evitar esto, la capacidad de ejecutar código en ensamblados cargados desde un origen remoto está deshabilitada de forma predeterminada. De forma predeterminada, si intenta cargar <xref:System.IO.FileLoadException> un ensamblado remoto, se produce un mensaje con excepción como el siguiente:

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

Para cargar el ensamblado y ejecutar su código, debe:

- Cree explícitamente un entorno limitado para el ensamblado (consulte [Cómo: Ejecutar código](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)de confianza parcial en un espacio aislado ).

- Ejecute el código del ensamblado con plena confianza. Para ello, configure `<loadFromRemoteSources>` el elemento. Le permite especificar que los ensamblados que se ejecutan en confianza parcial en versiones anteriores de .NET Framework ahora se ejecutan en plena confianza en .NET Framework 4 y versiones posteriores.

> [!IMPORTANT]
> Si el ensamblado no debe ejecutarse con plena confianza, no establezca este elemento de configuración. En su lugar, <xref:System.AppDomain> cree un espacio aislado en el que cargar el ensamblado.

El `enabled` atributo `<loadFromRemoteSources>` del elemento solo es efectivo cuando se deshabilita la seguridad de acceso al código (CAS). De forma predeterminada, la directiva CAS está deshabilitada en .NET Framework 4 y versiones posteriores. Si establece `enabled` `true`en , se concede plena confianza a los ensamblados remotos.

Si `enabled` no se `true`establece <xref:System.IO.FileLoadException> en , a se lanza en cualquiera de las siguientes condiciones:

- El comportamiento de espacio aislado del dominio actual es diferente de su comportamiento en .NET Framework 3.5. Esto requiere que la directiva CAS se deshabilite y que el dominio actual no se va en espacio aislado.

- El ensamblado que se `MyComputer` está cargando no es de la zona.

Establecer `<loadFromRemoteSources>` el `true` elemento para evitar que se produzca esta excepción. Le permite especificar que no confía en Common Language Runtime para habilitar los ensamblados cargados para la seguridad y que se les puede permitir ejecutar con plena confianza.

## <a name="notes"></a>Notas

- En .NET Framework 4.5 y versiones posteriores, los ensamblados de recursos compartidos de red local se ejecutan con plena confianza de forma predeterminada; no es necesario habilitar `<loadFromRemoteSources>` el elemento.

- Si una aplicación se ha copiado de la web, Windows la marca como una aplicación web, incluso si reside en el equipo local. Puede cambiar esa designación cambiando sus `<loadFromRemoteSources>` propiedades de archivo o puede usar el elemento para conceder al ensamblado plena confianza. Como alternativa, puede usar <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> el método para cargar un ensamblado local que el sistema operativo ha marcado como que se ha cargado desde la web.

- Puede obtener <xref:System.IO.FileLoadException> un en una aplicación que se ejecuta en una aplicación de PC virtual de Windows. Esto puede suceder cuando intenta cargar un archivo de carpetas vinculadas en el equipo de hospedaje. También puede ocurrir cuando intenta cargar un archivo desde una carpeta vinculada a través de Servicios de [Escritorio remoto](/windows/win32/termserv/terminal-services-portal) (Servicios de Terminal Server). Para evitar la `enabled` excepción, establezca en `true`.

## <a name="configuration-file"></a>Archivo de configuración

Este elemento se utiliza normalmente en el archivo de configuración de la aplicación, pero se puede utilizar en otros archivos de configuración en función del contexto. Para obtener más información, vea el artículo [Usos más implícitos de la directiva CAS: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) en el blog de seguridad de .NET.  

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo conceder plena confianza a los ensamblados cargados desde orígenes remotos.

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a>Consulte también

- [Usos más implícitos de la directiva CAS: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [Cómo: Ejecutar código de confianza parcial en un espacio aislado](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema del archivo de configuración](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

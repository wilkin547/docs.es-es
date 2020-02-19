---
title: <loadFromRemoteSources> (Elemento)
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: 454314bf1002a9648f669cc708c8ac42461fccaf
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452271"
---
# <a name="loadfromremotesources-element"></a>\<elemento > loadFromRemoteSources
Especifica si se debe conceder plena confianza a los ensamblados cargados desde orígenes remotos en .NET Framework 4 y versiones posteriores.
  
> [!NOTE]
> Si se le dirigió a este artículo debido a un mensaje de error en la lista de errores del proyecto de Visual Studio o un error de compilación, consulte [Cómo: usar un ensamblado desde la web en Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<loadFromRemoteSources >**  
  
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
  
## <a name="enabled-attribute"></a>atributo Enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|No conceda plena confianza a las aplicaciones de orígenes remotos. Este es el valor predeterminado.|  
|`true`|Conceda plena confianza a las aplicaciones desde orígenes remotos.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Observaciones

En el .NET Framework 3,5 y versiones anteriores, si carga un ensamblado desde una ubicación remota, el código del ensamblado se ejecuta en confianza parcial con un conjunto de permisos concedidos que depende de la zona desde la que se carga. Por ejemplo, si carga un ensamblado desde un sitio web, se carga en la zona de Internet y se le concede el conjunto de permisos de Internet. En otras palabras, se ejecuta en un espacio aislado de Internet.

A partir de la .NET Framework 4, la Directiva de seguridad de acceso del código (CAS) está deshabilitada y los ensamblados se cargan con plena confianza. Normalmente, esto concedería plena confianza a los ensamblados cargados con el método de <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> que anteriormente tenía un espacio aislado. Para evitar esto, la capacidad de ejecutar código en los ensamblados cargados desde un origen remoto está deshabilitada de forma predeterminada. De forma predeterminada, si intenta cargar un ensamblado remoto, se produce una <xref:System.IO.FileLoadException> con un mensaje de excepción similar al siguiente:

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

Para cargar el ensamblado y ejecutar su código, debe:

- Cree explícitamente un espacio aislado para el ensamblado (consulte [Cómo: ejecutar código de confianza parcial en un espacio aislado](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).

- Ejecute el código del ensamblado con plena confianza. Para ello, configure el elemento `<loadFromRemoteSources>`. Le permite especificar que los ensamblados que se ejecutan en confianza parcial en versiones anteriores del .NET Framework ahora se ejecutan en plena confianza en el .NET Framework 4 y versiones posteriores.

> [!IMPORTANT]
> Si el ensamblado no debe ejecutarse con plena confianza, no establezca este elemento de configuración. En su lugar, cree un <xref:System.AppDomain> en espacio aislado en el que cargar el ensamblado.

El atributo `enabled` del elemento `<loadFromRemoteSources>` solo es efectivo cuando está deshabilitada la seguridad de acceso del código (CAS). De forma predeterminada, la Directiva CAS está deshabilitada en el .NET Framework 4 y versiones posteriores. Si establece `enabled` en `true`, se concederá plena confianza a los ensamblados remotos.

Si `enabled` no se establece en `true`, se produce una <xref:System.IO.FileLoadException> en cualquiera de las siguientes condiciones:

- El comportamiento de espacio aislado del dominio actual es diferente de su comportamiento en el .NET Framework 3,5. Esto requiere que la Directiva de CAS esté deshabilitada y que el dominio actual no esté en un espacio aislado.

- El ensamblado que se está cargando no es de la zona `MyComputer`.

Establecer el elemento de `<loadFromRemoteSources>` en `true` impide que se inicie esta excepción. Permite especificar que no se confíe en el Common Language Runtime para crear un espacio aislado de seguridad de los ensamblados cargados y que se puedan ejecutar con plena confianza.

## <a name="notes"></a>Notas

- En el .NET Framework 4,5 y versiones posteriores, los ensamblados de recursos compartidos de red locales se ejecutan de forma predeterminada en plena confianza. no es necesario habilitar el elemento `<loadFromRemoteSources>`.

- Si se ha copiado una aplicación de la web, Windows la marca como una aplicación Web, aunque se encuentre en el equipo local. Puede cambiar esa designación cambiando sus propiedades de archivo, o puede usar el elemento `<loadFromRemoteSources>` para conceder plena confianza al ensamblado. Como alternativa, puede utilizar el método <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> para cargar un ensamblado local que el sistema operativo ha marcado como cargado desde Internet.

- Puede obtener un <xref:System.IO.FileLoadException> en una aplicación que se ejecuta en una aplicación de Windows Virtual PC. Esto puede ocurrir cuando se intenta cargar un archivo desde carpetas vinculadas en el equipo host. También se puede producir al intentar cargar un archivo desde una carpeta vinculada a través de [servicios de escritorio remoto](/windows/win32/termserv/terminal-services-portal) (Terminal Services). Para evitar la excepción, establezca `enabled` en `true`.

## <a name="configuration-file"></a>Archivo de configuración

Este elemento se utiliza normalmente en el archivo de configuración de la aplicación, pero se puede usar en otros archivos de configuración en función del contexto. Para obtener más información, vea el artículo [uso más implícito de la Directiva CAS: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) en el blog de seguridad de .net.  

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

- [Usos más implícitos de la Directiva CAS: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [Cómo: Ejecutar código de confianza parcial en un espacio aislado](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

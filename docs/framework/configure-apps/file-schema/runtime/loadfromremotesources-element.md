---
title: '&lt;loadFromRemoteSources&gt; elemento'
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a8858059159edddb4456561719c572fb9268be7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509488"
---
# <a name="ltloadfromremotesourcesgt-element"></a>&lt;loadFromRemoteSources&gt; elemento
Especifica si los ensamblados cargados desde orígenes remotos se deben conceder plena confianza en .NET Framework 4 y versiones posteriores.
  
> [!NOTE]
>  Si llega a este tema debido a un mensaje de error en la lista de errores del proyecto de Visual Studio o un error de compilación, véase [Cómo: usar un ensamblado desde la Web en Visual Studio](https://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).  
  
 \<configuration>  
\<en tiempo de ejecución >  
\<loadFromRemoteSources>  
  
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
|`enabled`|Atributo necesario.<br /><br /> Especifica si un ensamblado que se carga desde un origen remoto se debe conceder plena confianza.|  
  
## <a name="enabled-attribute"></a>atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|No conceda a plena confianza a las aplicaciones desde orígenes remotos. Este es el valor predeterminado.|  
|`true`|Conceder plena confianza a las aplicaciones desde orígenes remotos.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios

En .NET Framework 3.5 y versiones anteriores, si carga un ensamblado desde una ubicación remota, el código en el ensamblado se ejecuta en confianza parcial con un conjunto de permisos que depende de la zona desde la que se carga. Por ejemplo, si carga un ensamblado desde un sitio Web, se cargan en la zona de Internet y a conceder el conjunto de permisos de Internet. En otras palabras, ejecuta en un espacio aislado de Internet.

A partir de .NET Framework 4, se deshabilita la directiva de seguridad (CA) de acceso de código y los ensamblados se cargan con plena confianza. Normalmente, esto podría conceder plena confianza a los ensamblados cargados con los <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> método que anteriormente había sido en espacio aislado. Para evitar esto, la capacidad para ejecutar código en los ensamblados cargados desde un origen remoto está deshabilitada de forma predeterminada. De forma predeterminada, si intenta cargar un ensamblado remoto, un <xref:System.IO.FileLoadException> con un mensaje de excepción que se produce lo siguiente:

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

Para cargar el ensamblado y ejecutar su código, debe:

- Cree explícitamente un espacio aislado para el ensamblado (vea [Cómo: ejecutar código de confianza parcial en un espacio aislado](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).

- Ejecutar código de ensamblado de plena confianza. Ello, configure el `<loadFromRemoteSources>` elemento. Le permite especificar que los ensamblados que se ejecutan en confianza parcial en versiones anteriores de .NET Framework ahora se ejecutan con plena confianza en .NET Framework 4 y versiones posteriores.

> [!IMPORTANT]
> Si el ensamblado no se ejecutará con plena confianza, no establezca este elemento de configuración. En su lugar, cree un espacio aislado <xref:System.AppDomain> en el que se va a cargar el ensamblado.

El `enabled` atributo para el `<loadFromRemoteSources>` elemento es efectiva únicamente cuando seguridad de acceso del código (CAS) está deshabilitado. De forma predeterminada, la directiva CAS está deshabilitada en el .NET Framework 4 y versiones posteriores. Si establece `enabled` a `true`, ensamblados remotos gozan de plena confianza.

Si `enabled` no está establecido en `true`, un <xref:System.IO.FileLoadException> se produce en cualquiera de las condiciones siguientes:

- El comportamiento de espacio aislado del dominio actual es diferente de su comportamiento en .NET Framework 3.5. Esto requiere la directiva CAS va a deshabilitar y el dominio actual que no sea espacio aislado.

- El ensamblado que se está cargando no es de la `MyComputer` zona.

Establecer el `<loadFromRemoteSources>` elemento `true` impide que se produzca esta excepción. Permite especificar que no se basa en common language runtime para el espacio aislado los ensamblados cargados por seguridad, y que puede ser pueden ejecutarse en plena confianza.

## <a name="notes"></a>Notas

- En .NET Framework 4.5 y versiones posteriores, los ensamblados de recursos compartidos de red local se ejecutan con plena confianza de forma predeterminada; no es necesario que habilitar el `<loadFromRemoteSources>` elemento.

- Si una aplicación se ha copiado desde la web, se marca por Windows como una aplicación web, incluso si se encuentra en el equipo local. Puede cambiar esa designación cambiando sus propiedades de archivo, o puede usar el `<loadFromRemoteSources>` elemento que se va a conceder el ensamblado de plena confianza. Como alternativa, puede usar el <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> método para cargar un ensamblado local que el sistema operativo ha marcado como cargado desde la web.

- Es posible que obtenga un <xref:System.IO.FileLoadException> en una aplicación que se ejecuta en una aplicación de Windows Virtual PC. Esto puede ocurrir cuando se intenta cargar un archivo de carpetas vinculadas en el equipo host. También puede producirse cuando intenta cargar un archivo desde una carpeta vinculada sobre [servicios de escritorio remoto](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services). Para evitar la excepción, establezca `enabled` a `true`.

## <a name="configuration-file"></a>Archivo de configuración

Este elemento se utiliza normalmente en el archivo de configuración de aplicación, pero se puede usar en otros archivos de configuración según el contexto. Para obtener más información, vea el artículo [más implícita usa de la directiva CAS: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) en el blog de seguridad. NET.  

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra cómo conceder plena confianza a los ensamblados cargados desde orígenes remotos.

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a>Vea también

[Los usos más implícitos de la directiva CAS: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839)  
[Cómo: Ejecutar código de confianza parcial en un espacio aislado](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
[Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
[Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  

---
title: '&lt;loadFromRemoteSources&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acd66cdff9f2c68e7d665b1fd236b18eeb9b4bac
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2018
---
# <a name="ltloadfromremotesourcesgt-element"></a>&lt;loadFromRemoteSources&gt; elemento
Especifica si los ensamblados de orígenes remotos se deben conceder plena confianza.  
  
> [!NOTE]
>  Si llega a este tema debido a un mensaje de error en la lista de errores del proyecto de Visual Studio o un error de compilación, consulte [Cómo: usar un ensamblado desde el Web en Visual Studio](http://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).  
  
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
|`enabled`|Atributo necesario.<br /><br /> Especifica si un ensamblado que se carga desde orígenes remotos se debe conceder plena confianza.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|¿Concede plena confianza a las aplicaciones de orígenes remotos. Este es el valor predeterminado.|  
|`true`|Conceder plena confianza a las aplicaciones de orígenes remotos.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 En la versión de .NET Framework 3.5 y versiones anteriores, si carga un ensamblado desde una ubicación remota, el ensamblado se ejecutaba con confianza parcial con un conjunto de permisos que dependía de la zona en la que se cargó. Por ejemplo, si carga un ensamblado desde un sitio Web, se ha cargado en la zona de Internet y le concede el conjunto de permisos de Internet. En otras palabras, ejecuta en un espacio aislado de Internet. Si intenta ejecutar ese ensamblado en el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] y versiones posteriores, se produce una excepción, debe crear explícitamente un espacio aislado para el ensamblado (vea [Cómo: ejecutar código de confianza parcial en un espacio aislado](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)), o se ejecuta con plena confianza.  
  
 El `<loadFromRemoteSources>` elemento le permite especificar que los ensamblados que se hubieran producido confianza parcial en versiones anteriores de .NET Framework deben ejecutar como de plena confianza en el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] y versiones posteriores. De forma predeterminada, los ensamblados remotos no se ejecutan en el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] y versiones posteriores. Para ejecutar un ensamblado remoto, debe ejecutar como de plena confianza o crear un espacio aislado <xref:System.AppDomain> en el que se va a ejecutar.  
  
> [!NOTE]
>  En el [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], ensamblados a los recursos compartidos de red local se ejecutan como de plena confianza de forma predeterminada; no es necesario habilitar la `<loadFromRemoteSources>` elemento.  
  
> [!NOTE]
>  Si una aplicación se ha copiado desde el sitio web, se marca por Windows como una aplicación web, incluso si se encuentra en el equipo local. Puede cambiar esa designación cambiando las propiedades del archivo, o puede usar el `<loadFromRemoteSources>` elemento que se va a conceder el ensamblado de plena confianza. Como alternativa, puede utilizar el <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> método para cargar un ensamblado local que el sistema operativo haya marcado como se ha cargado desde la web.  
  
 El `enabled` de atributo para este elemento es efectivo únicamente cuando la seguridad de acceso del código (CAS) está deshabilitada. De forma predeterminada, la directiva CAS está deshabilitada en el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] y versiones posteriores. Si establece `enabled` a `true`, aplicaciones remotas gozan de plena confianza.  
  
 Si `<loadFromRemoteSources>` `enabled` no está establecido en `true`, se produce una excepción en las siguientes condiciones:  
  
-   El comportamiento de espacio aislado del dominio actual es diferente de su comportamiento en el [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)]. Esto requiere la directiva de entidades emisoras de certificados que se deshabilite y el dominio actual no sea en un espacio aislado.  
  
-   No es el ensamblado que se va a cargar desde el `MyComputer` zona.  
  
> [!NOTE]
>  Es posible que obtenga un <xref:System.IO.FileLoadException> en una aplicación de Windows Virtual PC cuando se intenta cargar un archivo desde carpetas vinculadas en el equipo que hospeda. Este error también puede producirse al intentar cargar un archivo desde una carpeta vinculada sobre [servicios de escritorio remoto](http://go.microsoft.com/fwlink/?LinkId=182775) (servicios de Terminal Server). Para evitar la excepción, establezca `enabled` a `true`.  
  
 Establecer el `<loadFromRemoteSources>` elemento `true` impide que se produzca esta excepción. Le permite especificar que no se basa en common language runtime para el espacio aislado los ensamblados cargados por seguridad y que se pueden ejecutar como de plena confianza.  
  
> [!IMPORTANT]
>  Si el ensamblado no debe ejecutarse con plena confianza, no establezca este elemento de configuración. En su lugar, cree un espacio aislado <xref:System.AppDomain> en el que se va a cargar el ensamblado.  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se utiliza normalmente en el archivo de configuración de aplicación, pero puede utilizarse en otros archivos de configuración según el contexto. Para obtener más información, vea el artículo [más implícita usa de la directiva CAS: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) en el blog de seguridad de. NET.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo conceder plena confianza a las aplicaciones de orígenes remotos.  
  
```xml  
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Los usos más implícitos de directiva CAS: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839)  
 [Cómo: Ejecutar código de confianza parcial en un espacio aislado](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)

---
description: -appconfig (Opciones del compilador de C#)
title: -appconfig (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /appconfig
helpviewer_keywords:
- /appconfig compiler option [C#]
- -appconfig compiler option [C#]
- appconfig compiler option [C#]
ms.assetid: 1cdbcbcc-7813-4010-b5b8-e67c107c5a98
ms.openlocfilehash: 8ee481851dc02bed5eb0a7c26fa8893e52d54a9f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157972"
---
# <a name="-appconfig-c-compiler-options"></a>-appconfig (Opciones del compilador de C#)

La opción del compilador **-appconfig** permite a una aplicación de C# especificar la ubicación del archivo de configuración de la aplicación de un ensamblado (app.config) al Common Language Runtime (CLR) en tiempo de enlace del ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-appconfig:file  
```  
  
## <a name="arguments"></a>Argumentos  

 `file`  
 Obligatorio. El archivo de configuración de la aplicación que contiene los valores de enlace del ensamblado.  
  
## <a name="remarks"></a>Comentarios  

 Un uso de **-appconfig** es el de escenarios avanzados en los que un ensamblado tiene que hacer referencia a la versión de .NET Framework y a la versión de .NET Framework para Silverlight de un ensamblado de referencia determinado al mismo tiempo. Por ejemplo, un diseñador de XAML escrito en Windows Presentation Foundation (WPF) podría tener que hacer referencia al escritorio de WPF, para la interfaz de usuario del diseñador, y al subconjunto de WPF que se incluye con Silverlight. El mismo ensamblado del diseñador tiene que tener acceso a ambos ensamblados. De forma predeterminada, las referencias independientes producen un error del compilador, ya que el enlace del ensamblado considera los dos ensamblados equivalentes.  
  
 La opción del compilador **-appconfig** permite especificar la ubicación de un archivo app.config que deshabilita el comportamiento predeterminado usando una etiqueta `<supportPortability>`, como se muestra en el siguiente ejemplo.  
  
 `<supportPortability PKT="7cec85d7bea7798e" enable="false"/>`  
  
 El compilador pasa la ubicación del archivo a la lógica de enlace del ensamblado de CLR.  
  
> [!NOTE]
> Si está usando Microsoft Build Engine (MSBuild) para compilar su aplicación, puede establecer la opción del compilador **-appconfig** mediante la adición de una etiqueta de propiedad al archivo .csproj. Para usar el archivo app.config que ya está establecido en el proyecto, agregue la etiqueta `<UseAppConfigForCompiler>` de propiedades al archivo .csproj y establezca su valor en `true`. Para especificar otro archivo app.config, agregue la etiqueta `<AppConfigForCompiler>` de propiedades y establezca su valor en la ubicación del archivo.  
  
## <a name="example"></a>Ejemplo  

 En el siguiente ejemplo se muestra un archivo app.config que permite a una aplicación tener referencias a la implementación de .NET Framework y de .NET Framework para Silverlight de cualquier ensamblado de .NET Framework que exista en ambas implementaciones. La opción del compilador **-appconfig** especifica la ubicación de este archivo app.config.  
  
```xml  
<configuration>  
      <runtime>  
      <assemblyBinding>  
            <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
            <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
      </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Elemento \<supportPortability>](../../../framework/configure-apps/file-schema/runtime/supportportability-element.md)
- [Opciones del compilador de C#, por orden alfabético](./listed-alphabetically.md)

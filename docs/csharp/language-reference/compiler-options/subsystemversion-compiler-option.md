---
title: "-subsystemversion (opciones del compilador de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# /subsystemversion (Opciones del compilador de C#)
Especifica la versión mínima del subsistema en el que puede ejecutar el archivo ejecutable generado, que determinan las versiones de Windows en el que puede ejecutar el archivo ejecutable. Normalmente, esta opción garantiza que el archivo ejecutable puede aprovechar las características de seguridad determinada que no están disponibles en versiones anteriores de Windows.  
  
> [!NOTE]
>  Para especificar que el subsistema de sí mismo, use el [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) opción del compilador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a>Parámetros  
 `major.minor`  
 La versión mínima necesaria del subsistema, como se expresa en una notación de puntos para las versiones principales y secundarias. Por ejemplo, puede especificar que una aplicación no se puede ejecutar en un sistema operativo que sea anterior a Windows 7 si establece el valor de esta opción en 6.01, como se describe en la tabla más adelante en este tema. Debe especificar los valores de `major` y `minor` como enteros.  
  
 Líder en ceros el `minor` versión no cambia la versión, pero hacer los ceros finales. Por ejemplo, 6.1 y 6.01 hacen referencia a la misma versión, pero 6.10 hace referencia a una versión diferente. Se recomienda que expresa la versión secundaria como dos dígitos para evitar confusiones.  
  
## <a name="remarks"></a>Comentarios  
 En la tabla siguiente se enumera las versiones de subsistema comunes de Windows.  
  
|Versión de Windows|Versión del subsistema|  
|---------------------|-----------------------|  
|Windows 2000|5.00|  
|Windows XP|5.01|  
|Windows Server 2003|5.02|  
|Windows Vista|6.00|  
|Windows 7|6.01|  
|Windows Server 2008|6.01|  
|[!INCLUDE[win8](../../../csharp/language-reference/compiler-options/includes/win8-md.md)]|6.02|  
  
## <a name="default-values"></a>Valores predeterminados  
 El valor predeterminado de la **/subsystemversion** opción del compilador depende de las condiciones de la lista siguiente:  
  
-   El valor predeterminado es 6.02 si se establece ninguna opción del compilador en la lista siguiente:  
  
    -   [/ target: appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
  
    -   [/ target: winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
  
    -   [/Platform:ARM](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)  
  
-   El valor predeterminado es 6.00 si utiliza MSBuild, escribimos [!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net-v45-md.md)], y no ha configurado ninguna de las opciones del compilador que se especificaron anteriormente en esta lista.  
  
-   El valor predeterminado es 4.00 si ninguna de las anteriores condiciones es true.  
  
## <a name="setting-this-option"></a>Establecer esta opción  
 Para establecer el **/subsystemversion** opción del compilador en Visual Studio, debe abrir el archivo .csproj y especifique un valor para el `SubsystemVersion` propiedad en el XML de MSBuild. No se puede establecer esta opción en el IDE de Visual Studio. Para obtener más información, vea "Valores predeterminados" anteriormente en este tema o [Common MSBuild Project Properties](/visual-studio/msbuild/common-msbuild-project-properties).  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)
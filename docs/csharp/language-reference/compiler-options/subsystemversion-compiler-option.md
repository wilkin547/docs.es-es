---
title: -subsystemversion (Opciones del compilador de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8766904cad739b29c7dfe80b29305ea2b3bd2e6f
ms.lasthandoff: 03/13/2017

---
# <a name="subsystemversion-c-compiler-options"></a>/subsystemversion (Opciones del compilador de C#)
Especifica la versión mínima del subsistema en la que se puede ejecutar el archivo ejecutable generado, lo que determina las versiones de Windows en las que se puede ejecutar el archivo ejecutable. Normalmente, esta opción garantiza que el archivo ejecutable pueda aprovechar las características de seguridad concretas que no están disponibles en versiones anteriores de Windows.  
  
> [!NOTE]
>  Para especificar el subsistema en sí mismo, use la opción del compilador [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a>Parámetros  
 `major.minor`  
 La versión mínima requerida del subsistema, expresada en una notación de puntos para las versiones principales y secundarias. Por ejemplo, puede especificar que una aplicación no se puede ejecutar en un sistema operativo que sea anterior a Windows 7 si establece el valor de esta opción en 6.01, como se describe en la tabla que aparece más adelante en este tema. Debe especificar los valores de `major` y `minor` como números enteros.  
  
 Los ceros a la izquierda en la versión `minor` no cambian la versión, pero los ceros a la derecha sí. Por ejemplo, 6.1 y 6.01 hacen referencia a la misma versión, pero 6.10 hace referencia a una versión diferente. Se recomienda expresar la versión secundaria como dos dígitos para evitar confusiones.  
  
## <a name="remarks"></a>Comentarios  
 En la tabla siguiente se enumeran las versiones de subsistema habituales de Windows.  
  
|Versión de Windows|Versión de subsistema|  
|---------------------|-----------------------|  
|Windows 2000|5.00|  
|Windows XP|5.01|  
|Windows Server 2003|5.02|  
|Windows Vista|6.00|  
|Windows 7|6.01|  
|Windows Server 2008|6.01|  
|[!INCLUDE[win8](../../../csharp/language-reference/compiler-options/includes/win8_md.md)]|6.02|  
  
## <a name="default-values"></a>Valores predeterminados  
 El valor predeterminado de la opción del compilador **/subsystemversion** depende de las condiciones de la siguiente lista:  
  
-   El valor predeterminado es 6.02 si se establece cualquier opción del compilador en la siguiente lista:  
  
    -   [/target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
  
    -   [/target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
  
    -   [/platform:arm](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)  
  
-   El valor predeterminado es 6.00 si usa MSBuild, tiene como destino [!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net_v45_md.md)] y no ha configurado ninguna de las opciones del compilador que se han especificado anteriormente en esta lista.  
  
-   El valor predeterminado es 4.00 si no se cumple ninguna de las condiciones anteriores.  
  
## <a name="setting-this-option"></a>Establecer esta opción  
 Para establecer la opción del compilador **/subsystemversion** en Visual Studio, debe abrir el archivo .csproj y especificar un valor para la propiedad `SubsystemVersion` en el XML de MSBuild. No se puede establecer esta opción en el IDE de Visual Studio. Para obtener más información, consulte la sección "Valores predeterminados" que aparece más arriba en este tema o [Propiedades comunes de proyectos de MSBuild](https://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties).  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)

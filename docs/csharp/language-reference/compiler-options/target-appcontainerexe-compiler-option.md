---
description: -target:appcontainerexe (Opciones del compilador de C#)
title: -target:appcontainerexe (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
ms.openlocfilehash: 8c3b85c2f5a20788bd311e9bf3b300c32967da77
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128587"
---
# <a name="-targetappcontainerexe-c-compiler-options"></a>-target:appcontainerexe (Opciones del compilador de C#)
Si usa la opción del compilador **-target:appcontainerexe**, este crea un archivo ejecutable de Windows (.exe) que se debe ejecutar en un contenedor de la aplicación. Esta opción equivale a [-target:winexe](./target-winexe-compiler-option.md), pero está diseñada para las aplicaciones de la Tienda Windows 8.x.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-target:appcontainerexe  
```  
  
## <a name="remarks"></a>Observaciones  
 Para exigir que la aplicación se ejecute en un contenedor de la aplicación, esta opción establece un bit en el archivo [portable ejecutable](/windows/desktop/Debug/pe-format) (PE). Cuando se establece ese bit, se produce un error si el método CreateProcess intenta iniciar el archivo ejecutable fuera de un contenedor de la aplicación.  
  
 A menos que use la opción [-out](./out-compiler-option.md), el archivo de salida toma el nombre del archivo de entrada que contiene el método [Main](../../programming-guide/main-and-command-args/index.md).  
  
 Cuando se especifica esta opción en un símbolo del sistema, todos los archivos hasta la siguiente opción **-out** o **-target** se usan para crear el archivo ejecutable.  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a>Para establecer esta opción del compilador en el IDE  
  
1. En el **Explorador de soluciones**, abra el menú contextual del proyecto y después elija **Propiedades**.  
  
2. En la pestaña **Aplicación**, en la lista **Tipo de resultado**, elija **Aplicación de la Tienda Windows**.  
  
     Esta opción solo está disponible para las plantillas de aplicaciones de la Tienda Windows 8.x.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente compila `filename.cs` en un archivo ejecutable de Windows que solo se puede ejecutar en un contenedor de la aplicación.  
  
```console  
csc -target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a>Vea también

- [-target (Opciones del compilador de C#)](./target-compiler-option.md)
- [-target:winexe (Opciones del compilador de C#)](./target-winexe-compiler-option.md)
- [Opciones del compilador de C#](./index.md)

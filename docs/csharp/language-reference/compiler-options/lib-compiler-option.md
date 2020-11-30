---
description: -lib (Opciones del compilador de C#)
title: -lib (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /lib
helpviewer_keywords:
- lib compiler option [C#]
- -lib compiler option [C#]
- /lib compiler option [C#]
ms.assetid: b0efcc88-e8aa-4df4-a00b-8bdef70b7673
ms.openlocfilehash: 9478501ea98ec1b9d3ec2761bc4ebf3f6bef656c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "91152447"
---
# <a name="-lib-c-compiler-options"></a>-lib (Opciones del compilador de C#)

La opción **-lib** especifica la ubicación de los ensamblados a los que se hace referencia mediante la opción [-reference (Opciones del compilador de C#)](./reference-compiler-option.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-lib:dir1[,dir2]  
```  
  
## <a name="arguments"></a>Argumentos  

 `dir1`  
 Un directorio para el compilador para buscar un ensamblado al que se hace referencia si no lo encuentra en el directorio de trabajo actual (el directorio desde el que se invoca al compilador) o en el directorio del sistema de Common Language Runtime.  
  
 `dir2`  
 Uno o varios directorios adicionales para buscar las referencias a ensamblados. Separe los nombres de directorio adicionales con una coma y sin espacio en blanco entre ellos.  
  
## <a name="remarks"></a>Observaciones  

 El compilador busca referencias a ensamblados que no presentan la ruta completa en el siguiente orden:  
  
1. Directorio de trabajo actual. Es el directorio desde donde se invoca al compilador.  
  
2. El directorio del sistema de Common Language Runtime.  
  
3. Directorios especificados por **-lib**.  
  
4. Directorios especificados por la variable de entorno LIB.  
  
 Use **-reference** para especificar una referencia a un ensamblado.  
  
 La opción **-lib** es sumatoria; si se especifica más de una vez, se anexa a valores ya existentes.  
  
 Una alternativa al uso de **-lib** consiste en copiar los ensamblados necesarios en el directorio de trabajo; esto permitirá pasar el nombre del ensamblado a **-reference**. Después, se pueden eliminar los ensamblados del directorio de trabajo. Dado que en el manifiesto del ensamblado no se especifica la ruta al ensamblado dependiente, la aplicación puede iniciarse en el equipo de destino y desde allí buscará y usará el ensamblado en la caché global de ensamblados.  
  
 El hecho de que el compilador puede hacer referencia al ensamblado no implica que Common Language Runtime pueda buscar y cargar el ensamblado en tiempo de ejecución. Vea [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../framework/deployment/how-the-runtime-locates-assemblies.md) para obtener los detalles sobre cómo busca el motor en tiempo de ejecución los ensamblados a los que se hace referencia.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Abra el cuadro de diálogo **Páginas de propiedades** del proyecto.  
  
2. Haga clic en la página de propiedades **Ruta de acceso de referencias**.  
  
3. Modifique el contenido del cuadro de lista.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>.  
  
## <a name="example"></a>Ejemplo  

 Compile t2.cs para crear un archivo .exe. El compilador buscará referencias a ensamblados en el directorio de trabajo y en el directorio raíz de la unidad C.  
  
```console  
csc -lib:c:\ -reference:t2.dll t2.cs  
```  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)

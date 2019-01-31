---
title: Un valor de tipo '<typename1>' no se puede convertir a '<typename2>' (varias referencias de archivo)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: e394459e7d25d38e27e78f10dd547cb9ebd6230d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261352"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2-multiple-file-references"></a>Valor de tipo '\<typename1 >' no se puede convertir a '\<nombredetipo2 >' (varias referencias de archivo)
Valor de tipo '\<typename1 >' no se puede convertir a '\<nombredetipo2 >'. Discordancia de tipos podría ser debido a la combinación de una referencia a '\<rutadeaccesodearchivo1 >' en el proyecto '\<projectname1 >' con una referencia a '\<rutadeaccesodearchivo2 >' en el proyecto '\<projectname2 >'. Si ambos ensamblados son idénticos, intente reemplazar estas referencias para que ambas procedan de la misma ubicación.  
  
 En una situación donde un proyecto realiza más de una referencia de archivo a un ensamblado, el compilador no puede garantizar que se puede convertir un tipo a otro.  
  
 Cada referencia de archivo especifica una ruta de acceso y nombre del archivo de salida de un proyecto (normalmente un archivo DLL). El compilador no puede garantizar que los archivos de salida procedan del mismo origen, o que representan la misma versión del mismo ensamblado. Por lo tanto, no puede garantizar que los tipos en las distintas referencias son del mismo tipo, o incluso que uno puede convertirse a otro.  
  
 Puede usar una referencia de archivo si sabe que los ensamblados de referencia tienen la misma identidad de ensamblado. La *identidad del ensamblado* incluye el nombre, la versión, la clave pública, si existe, y la referencia cultural del ensamblado. Esta información identifica de forma exclusiva el ensamblado.  
  
 **Identificador de error:** BC30961  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si los ensamblados de referencia tienen la misma identidad de ensamblado, quitar o reemplazar una de las referencias de archivo, por lo que hay solo una referencia de archivo.  
  
-   Si los ensamblados de referencia no tienen la misma identidad de ensamblado, a continuación, cambie el código para que no intenta convertir a un tipo de una a un tipo en el otro.  
  
## <a name="see-also"></a>Vea también
- [Conversiones de tipos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)


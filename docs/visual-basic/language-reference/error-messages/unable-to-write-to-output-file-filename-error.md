---
title: 'No se puede escribir en el archivo de salida &quot;&lt;nombre de archivo&gt;&quot;: &lt;error&gt; | Documentos de Microsoft'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31019
- bc31019
dev_langs:
- VB
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fe093ec3b36ba733cb9b0c162e242c8dce6b7c78
ms.lasthandoff: 03/13/2017

---
# <a name="unable-to-write-to-output-file-39ltfilenamegt39-lterrorgt"></a>No se puede escribir en el archivo de salida '&lt;nombre de archivo&gt;': &lt;error&gt;
Se ha producido un problema al crear el archivo.  
  
 No se puede abrir un archivo de salida para escritura. Puede que otro proceso haya abierto el archivo (o la carpeta que lo contiene) o puede que este tenga establecido el atributo de solo lectura.  
  
 A continuación indicamos las situaciones más habituales en la que un archivo se abre de forma exclusiva:  
  
-   La aplicación ya se está ejecutando y usando sus archivos. Para solucionar este problema, asegúrese de que la aplicación no se está ejecutando.  
  
-   Otra aplicación ha abierto el archivo. Para solucionar este problema, asegúrese de que ninguna otra aplicación está accediendo a los archivos. No siempre queda del todo claro qué aplicación está accediendo a los archivos; en tal caso, reiniciar el equipo constituye la forma más sencilla de finalizar la aplicación.  
  
 Esta excepción se generará aun cuando solo haya un archivo de salida del proyecto marcado como de solo lectura.  
  
 **Id. de error:** BC31019  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Vuelva a compilar el programa para ver si el error se repite.  
  
2.  Si el error continúa, guarde el trabajo y reinicie [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].  
  
3.  Si el error continúa, reinicie el equipo.  
  
4.  Si el error se repite, reinstale [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
5.  Si el error persiste después de la reinstalación, informe al respecto a los Servicios de soporte técnico de Microsoft.  
  
### <a name="to-check-file-attributes-in-file-explorer"></a>Para consultar los atributos de archivo en el Explorador de archivos  
  
1.  Abra la carpeta que le interese.  
  
2.  Haga clic en el **vistas** icono y elija **detalles**.  
  
3.  Haga clic en el encabezado de columna y elija **atributos** en la lista desplegable.  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a>Para cambiar los atributos de un archivo o carpeta  
  
1.  En **Explorador de archivos**, haga clic en el archivo o carpeta y elija **propiedades**.  
  
2.  En el **atributos** sección de la **General** ficha, desactive el **de sólo lectura** cuadro.  
  
3.  Press **OK**.  
  
## <a name="see-also"></a>Vea también  
 [Hable con nosotros](https://docs.microsoft.com/visualstudio/ide/talk-to-us)

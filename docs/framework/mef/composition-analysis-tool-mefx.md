---
title: Herramienta de análisis de composición (Mefx)
ms.date: 03/30/2017
helpviewer_keywords:
- Composition Analysis Tool [MEF]
- MEF, Composition Analysis Tool
- Mefx [MEF], Composition Analysis Tool
ms.assetid: c48a7f93-83bb-4a06-aea0-d8e7bd1502ad
ms.openlocfilehash: 7d0acf16ace5aad60b32b7139a58a258fb080ee0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181301"
---
# <a name="composition-analysis-tool-mefx"></a>Herramienta de análisis de composición (Mefx)
La herramienta de análisis de composición (Mefx) es una aplicación de línea de comandos que analiza los archivos de biblioteca (.dll) y los archivos de aplicación (.exe) que contienen elementos de Managed Extensibility Framework (MEF). El propósito principal de Mefx es ofrecer a los desarrolladores una manera de diagnosticar errores de composición en sus aplicaciones de MEF sin el engorro de tener que agregar código de seguimiento a la propia aplicación. También puede ser útil para ayudar a comprender los elementos de una biblioteca de terceros. En este tema se describe cómo usar Mefx y se proporciona una referencia de su sintaxis.  
  
<a name="getting_mefx"></a>
## <a name="getting-mefx"></a>Obtener Mefx  
 Mefx está disponible en GitHub, en [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef/releases/tag/4.0). Simplemente descargue y descomprima la herramienta.  
  
<a name="basic_syntax"></a>
## <a name="basic-syntax"></a>Sintaxis básica  
 Mefx se invoca desde la línea de comandos en el formato siguiente:  
  
```console
mefx [files and directories] [action] [options]  
```  
  
 El primer conjunto de argumentos especifica los archivos y los directorios desde los que se cargan elementos para el análisis. Especifique un archivo con el modificador `/file:` conmutador y un directorio con el modificador `/directory:` . Puede especificar varios archivos o directorios, tal como se muestra en el ejemplo siguiente:  
  
```console  
mefx /file:MyAddIn.dll /directory:Program\AddIns [action...]  
```  
  
> [!NOTE]
> Cada archivo .dll o .exe solo se debe cargar una vez. Si se carga un archivo varias veces, la herramienta puede devolver información incorrecta.  
  
 Después de crear la lista de archivos y directorios, especifique un comando y las opciones del mismo.  
  
<a name="listing_available_parts"></a>
## <a name="listing-available-parts"></a>Lista de los elementos disponibles  
 Use la acción `/parts` para enumerar todos los elementos declarados en los archivos cargados. El resultado es una lista de nombres de elementos.  
  
```console
mefx /file:MyAddIn.dll /parts  
MyAddIn.AddIn  
MyAddIn.MemberPart  
```  
  
 Para obtener más información sobre los elementos, use la opción `/verbose` . Esto proporcionará más información sobre todos los elementos disponibles. Para obtener más información sobre un único elemento, use la acción `/type` en lugar de `/parts`.  
  
```console  
mefx /file:MyAddIn.dll /type:MyAddIn.AddIn /verbose  
[Part] MyAddIn.MemberPart from: AssemblyCatalog (Assembly=" MyAddIn, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Export] MyAddIn.MemberPart (ContractName=" MyAddIn.MemberPart")  
```  
  
<a name="listing_imports_and_exports"></a>
## <a name="listing-imports-and-exports"></a>Lista de importaciones y exportaciones  
 Las acciones `/imports` y `/exports` enumerarán todos los elementos importados y exportados, respectivamente. También puede enumerar los elementos que importan o exportan un tipo determinado mediante las acciones `/importers` o `/exporters` .  
  
```console  
mefx /file:MyAddIn.dll /importers:MyAddin.MemberPart  
MyAddin.AddIn  
```  
  
 Asimismo, puede aplicar la opción `/verbose` a estas acciones.  
  
<a name="finding_rejected_parts"></a>
## <a name="finding-rejected-parts"></a>Búsqueda de elementos rechazados  
 Una vez cargados los elementos disponibles, Mefx usa el motor de composición de MEF para combinarlos. Los elementos que no se pueden componer correctamente se denominan elementos *rechazados*. Para enumerar todos los elementos rechazados, use la acción `/rejected` .  
  
 Puede usar la opción `/verbose` con la acción `/rejected` para imprimir información detallada sobre los elementos rechazados. En el ejemplo siguiente, la DLL `ClassLibrary1` contiene el elemento `AddIn` , que importa los elementos `MemberPart` y `ChainOne` . `ChainOne` importa `ChainTwo`, pero `ChainTwo` no existe. Esto significa que `ChainOne` se rechaza, lo que hace que `AddIn` también se rechace.  
  
```console  
mefx /file:ClassLibrary1.dll /rejected /verbose  
```  
  
 A continuación se muestra la salida completa del comando anterior:  
  
```output
[Part] ClassLibrary1.AddIn from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Export] ClassLibrary1.AddIn (ContractName="ClassLibrary1.AddIn")  
  [Import] ClassLibrary1.AddIn.memberPart (ContractName="ClassLibrary1.MemberPart")  
    [SatisfiedBy] ClassLibrary1.MemberPart (ContractName="ClassLibrary1.MemberPart") from: ClassLibrary1.MemberPart from: AssemblyCatalog (Assembly="ClassLibrar  
y1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Import] ClassLibrary1.AddIn.chain (ContractName="ClassLibrary1.ChainOne")  
    [Exception] System.ComponentModel.Composition.ImportCardinalityMismatchException: No valid exports were found that match the constraint '((exportDefinition.ContractName == "ClassLibrary1.ChainOne") AndAlso (exportDefinition.Metadata.ContainsKey("ExportTypeIdentity") AndAlso "ClassLibrary1.ChainOne".Equals(exportDefinition.Metadata.get_Item("ExportTypeIdentity"))))', invalid exports may have been rejected.  
   at System.ComponentModel.Composition.Hosting.ExportProvider.GetExports(ImportDefinition definition, AtomicComposition atomicComposition)  
   at Microsoft.ComponentModel.Composition.Diagnostics.CompositionInfo.AnalyzeImportDefinition(ExportProvider host, IEnumerable`1 availableParts, ImportDefinition id)  
    [Unsuitable] ClassLibrary1.ChainOne (ContractName="ClassLibrary1.ChainOne")  
from: ClassLibrary1.ChainOne from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
      [Because] PartDefinitionIsRejected, The part providing the export is rejected because of other issues.  
  
[Part] ClassLibrary1.ChainOne from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Primary Rejection]  
  [Export] ClassLibrary1.ChainOne (ContractName="ClassLibrary1.ChainOne")  
  [Import] ClassLibrary1.ChainOne.chain (ContractName="ClassLibrary1.ChainTwo")  
    [Exception] System.ComponentModel.Composition.ImportCardinalityMismatchException: No valid exports were found that match the constraint '((exportDefinition.ContractName == "ClassLibrary1.ChainTwo") AndAlso (exportDefinition.Metadata.ContainsKey("ExportTypeIdentity") AndAlso "ClassLibrary1.ChainTwo".Equals(exportDefinition.Metadata.get_Item("ExportTypeIdentity"))))', invalid exports may have been rejected.  
   at System.ComponentModel.Composition.Hosting.ExportProvider.GetExports(ImportDefinition definition, AtomicComposition atomicComposition)  
   at Microsoft.ComponentModel.Composition.Diagnostics.CompositionInfo.AnalyzeImportDefinition(ExportProvider host, IEnumerable`1 availableParts, ImportDefinition id)  
```  
  
 La información interesante se encuentra en los resultados de `[Exception]` y `[Unsuitable]` . El resultado de `[Exception]` proporciona información sobre el motivo de rechazo de un elemento. El resultado de `[Unsuitable]` indica por qué un elemento, que en otro caso se consideraría una coincidencia, no se pudo usar para rellenar una importación; en este caso, el motivo es que ese elemento también se rechazó para las importaciones que faltan.  
  
<a name="analyzing_primary_causes"></a>
## <a name="analyzing-primary-causes"></a>Analizar las causas principales  
 Si hay varios elementos vinculados en una cadena de dependencia larga, es posible que si se produce un problema en un elemento de la parte inferior, se rechace toda la cadena. Diagnosticar estos problemas puede ser difícil porque la causa principal del error no siempre está clara. Para ayudar a solucionar el problema, puede usar la acción `/causes` , que intenta encontrar la causa principal de cualquier rechazo en cascada.  
  
 Mediante la acción `/causes` del ejemplo anterior se mostraría únicamente la información de `ChainOne`, cuya importación sin rellenar es la causa principal del rechazo de `AddIn`. La acción `/causes` se puede usar en las opciones normal y `/verbose` .  
  
> [!NOTE]
> En la mayoría de los casos, Mefx podrá diagnosticar la causa principal de un error en cascada. Sin embargo, Mefx no podrá diagnosticar la causa en aquellos casos en que los elementos se agregan mediante programación a un contenedor, ni tampoco en los casos relacionados con contenedores jerárquicos o en los que hay implementaciones de `ExportProvider` personalizadas. En general, los casos descritos anteriormente deben evitarse siempre que sea posible, ya que los errores suelen ser difíciles de diagnosticar.  
  
<a name="white_lists"></a>
## <a name="white-lists"></a>Listas blancas  
 La opción `/whitelist` le permite especificar un archivo de texto que enumera los elementos que se esperan que se rechacen. De este modo, se marcarán los rechazos inesperados. Esto puede resultar útil al analizar una biblioteca incompleta o una biblioteca secundaria en la que falten algunas dependencias. La opción `/whitelist` puede aplicarse a las acciones `/rejected` o `/causes` .  
  
 Piense en un archivo llamado test.txt que contenga el texto “ClassLibrary1.ChainOne”. Si ejecuta la acción `/rejected` con la opción `/whitelist` en el ejemplo anterior, producirá la salida siguiente:  
  
```console
mefx /file:ClassLibrary1.dll /rejected /whitelist:test.txt  
[Unexpected] ClassLibrary1.AddIn  
ClassLibrary1.ChainOne  
```

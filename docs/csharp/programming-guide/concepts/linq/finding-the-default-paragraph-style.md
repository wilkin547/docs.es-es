---
title: Buscar el estilo de párrafo predeterminado (C#)
ms.date: 07/20/2015
ms.assetid: be102177-8ab0-444a-b671-7023e555ffdb
ms.openlocfilehash: 45a3e293a88fc0d7fc6aa70d21d1d3a6a8bb9b13
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204105"
---
# <a name="finding-the-default-paragraph-style-c"></a>Buscar el estilo de párrafo predeterminado (C#)
La primera tarea del tutorial Manipular información en un documento WordprocessingML consiste en buscar el estilo predeterminado de los párrafos del documento.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>DESCRIPCIÓN  
 El siguiente ejemplo abre un documento XML WordprocessingML abierto de Office, busca las partes del documento y del estilo del paquete y ejecuta una consulta que busca el nombre de estilo predeterminado. Para obtener información sobre los paquetes Office Open XML y las partes de las que constan, vea [Información de los documentos de WordprocessingML de Office Open XML (C#)](./wordprocessingml-document-with-styles.md).  
  
 La consulta busca un nodo con el nombre `w:style` que tiene un atributo con el nombre `w:type` con un valor de "paragraph" y también un atributo con el nombre `w:default` con un valor de "1". Puesto que sólo habrá un nodo XML con estos atributos, la consulta utiliza el operador <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> para convertir una recopilación en un singleton. A continuación obtiene el valor de un atributo con el nombre `w:styleId`.  
  
 Este ejemplo utiliza las clases que se encuentran en el ensamblado WindowsBase. Utiliza los tipos del espacio de nombres <xref:System.IO.Packaging?displayProperty=nameWithType>.  
  
### <a name="code"></a>Código  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship =  
      wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative),  
          docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation =  
          documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
        if (styleRelation != null)  
        {  
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
        }  
    }  
}  
  
// The following query finds all the paragraphs that have the default style.  
string defaultStyle =   
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
Console.WriteLine("The default style is: {0}", defaultStyle);  
```  
  
### <a name="comments"></a>Comentarios  
 Este ejemplo produce el siguiente resultado:  
  
```output  
The default style is: Normal  
```  
  
## <a name="next-steps"></a>Pasos siguientes  
 En el siguiente ejemplo, creará una consulta similar que busca todos los párrafos de un documento y sus estilos:  
  
- [Recuperar los párrafos y sus estilos (C#)](./retrieving-the-paragraphs-and-their-styles.md)  

---
title: "Практическое руководство. Определение изображения, отображаемого элементом управления Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6d9f4d806b39e6e1272ddbb60befdaf8c76e46b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Практическое руководство. Определение изображения, отображаемого элементом управления Windows Forms
Несколько элементов управления Windows Forms можно отображать изображения. Эти образы могут использоваться значки, поясняющие назначение элемента управления, например, значок дискеты на кнопке, отвечающий за **Сохранить** команды. Кроме того значок может быть фоновые изображения, чтобы предоставить элемент управления, внешний вид и поведение.  
  
### <a name="to-set-the-image-displayed-by-a-control"></a>Чтобы задать изображение, отображаемое на элементе управления  
  
1.  Задайте в качестве `Image` или `BackgroundImage` свойство для объекта типа <xref:System.Drawing.Image>. Как правило, будет загружаться изображение из файла с помощью <xref:System.Drawing.Image.FromFile%2A> метод.  
  
     В следующем примере кода путь задан при размещении изображения является **Мои рисунки** папки. Большинство компьютеров под управлением операционной системы Windows, содержат эту папку. Это также позволяет пользователям с уровнями доступа минимальные системные для безопасной работы приложения. В следующем примере кода требуется наличие формы с <xref:System.Windows.Forms.PictureBox> управления добавлен.  
  
    ```vb  
    ' Replace the image named below  
    ' with an icon of your own choosing.  
    PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.MyPictures) _  
       & "\Image.gif")  
    ```  
  
    ```csharp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.MyPictures)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    pictureBox1->Image = Image::FromFile(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::MyPictures),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>

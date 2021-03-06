---
title: (Visual Basic) 기간 이후 비동기 작업 취소
ms.date: 07/20/2015
ms.assetid: a48045a3-6a99-42af-b824-af340f0b9a5d
ms.openlocfilehash: 1be9f976c68db41526aea2fbf250ecd8c4e9521e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cancel-async-tasks-after-a-period-of-time-visual-basic"></a>(Visual Basic) 기간 이후 비동기 작업 취소
작업이 완료될 때까지 대기하지 않으려는 경우 일정 기간 후에 <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> 메서드를 사용하여 비동기 작업을 취소할 수 있습니다. 이 메서드는 `CancelAfter` 식으로 지정된 일정 기간 내에 완료되지 않은 연결된 작업의 취소를 예약합니다.  
  
 개발 하는 코드를 추가 하는이 예제 [는 목록의 작업 (Visual Basic) 또는 비동기 작업 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) 웹 사이트의 목록을 다운로드 하 고 각각의 내용의 길이 표시할 수 있습니다.  
  
> [!NOTE]
>  예제를 실행 하려면 Visual Studio 2012 이상 및.NET Framework 4.5가 있어야 하거나 나중에 컴퓨터에 설치 합니다.  
  
## <a name="downloading-the-example"></a>예제 다운로드  
 [Async 샘플: 응용 프로그램 세부 조정](http://go.microsoft.com/fwlink/?LinkId=255046)에서 전체 WPF(Windows Presentation Foundation) 프로젝트를 다운로드한 후 다음 단계를 따를 수 있습니다.  
  
1.  다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.  
  
3.  에 **프로젝트 열기** 대화 상자, 하면 압축을 푼 샘플 코드가 저장 된 폴더를 연 다음 AsyncFineTuningVB에 대 한 솔루션 (.sln) 파일을 엽니다.  
  
4.  **솔루션 탐색기**에서 **CancelAfterTime** 프로젝트에 대한 바로 가기 메뉴를 열고 **시작 프로젝트로 설정**을 선택합니다.  
  
5.  F5 키를 선택하여 프로젝트를 실행합니다.  
  
     디버그하지 않고 프로젝트를 실행하려면 Ctrl+F5를 선택합니다.  
  
6.  프로그램을 여러 번 실행하여 모든 웹 사이트 또는 일부 웹 사이트에 대한 출력이 표시되는지, 또는 웹 사이트에 대한 출력이 표시되지 않는지 확인합니다.  
  
 프로젝트를 다운로드 하지 않으려면 하는 경우이 항목의 끝에 MainWindow.xaml.vb 파일을 검토할 수 있습니다.  
  
## <a name="building-the-example"></a>예제 빌드  
 개발 하는 프로젝트에 추가 하는이 항목의 예제 [는 목록의 작업 (Visual Basic) 또는 비동기 작업 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) 작업 목록 취소 합니다. **취소** 단추는 명시적으로 사용되지 않지만 예제에서는 같은 UI를 사용합니다.  
  
 직접 예제를 빌드하려면 "예제 다운로드" 섹션의 지침을 단계별로 따르되, **CancelAListOfTasks**를 **시작 프로젝트**로 선택합니다. 이 항목의 변경 내용을 해당 프로젝트에 추가합니다.  
  
 작업이 취소됨으로 표시되기 전에 소요되는 최대 시간을 지정하려면 다음 예제와 같이 `CancelAfter` 호출을 `startButton_Click`에 추가합니다. 추가된 내용에는 별표가 표시됩니다.  
  
```vb  
Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)  
  
    ' Instantiate the CancellationTokenSource.  
    cts = New CancellationTokenSource()  
  
    resultsTextBox.Clear()  
  
    Try  
        ' ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You   
        ' can adjust the time.)  
        cts.CancelAfter(2500)  
  
        Await AccessTheWebAsync(cts.Token)  
        resultsTextBox.Text &= vbCrLf & "Downloads complete."  
  
    Catch ex As OperationCanceledException  
        resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf  
  
    Catch ex As Exception  
        resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf  
    End Try  
  
    ' Set the CancellationTokenSource to Nothing when the download is complete.  
    cts = Nothing  
End Sub  
```  
  
 프로그램을 여러 번 실행하여 모든 웹 사이트 또는 일부 웹 사이트에 대한 출력이 표시되는지, 또는 웹 사이트에 대한 출력이 표시되지 않는지 확인합니다. 다음은 샘플 출력입니다.  
  
```  
Length of the downloaded string: 35990.  
  
Length of the downloaded string: 407399.  
  
Length of the downloaded string: 226091.  
  
Downloads canceled.  
```  
  
## <a name="complete-example"></a>완성된 예제  
 다음 코드는 예제에 대 한 MainWindow.xaml.vb 파일의 전체 텍스트입니다. 별표는 이 예제에 대해 추가된 요소를 표시합니다.  
  
 <xref:System.Net.Http>에 대한 참조를 추가해야 합니다.  
  
 [Async 샘플: 응용 프로그램 미세 조정](http://go.microsoft.com/fwlink/?LinkId=255046)에서 프로젝트를 다운로드할 수 있습니다.  
  
```vb  
' Add an Imports directive and a reference for System.Net.Http.  
Imports System.Net.Http  
  
' Add the following Imports directive for System.Threading.  
Imports System.Threading  
  
Class MainWindow  
  
    ' Declare a System.Threading.CancellationTokenSource.  
    Dim cts As CancellationTokenSource  
  
    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)  
  
        ' Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
  
        resultsTextBox.Clear()  
  
        Try  
            ' ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You   
            ' can adjust the time.)  
            cts.CancelAfter(2500)  
  
            Await AccessTheWebAsync(cts.Token)  
            resultsTextBox.Text &= vbCrLf & "Downloads complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf  
        End Try  
  
        ' Set the CancellationTokenSource to Nothing when the download is complete.  
        cts = Nothing  
    End Sub  
  
    ' You can still include a Cancel button if you want to.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
  
    ' Provide a parameter for the CancellationToken.  
    ' Change the return type to Task because the method has no return statement.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task  
  
        Dim client As HttpClient = New HttpClient()  
  
        ' Call SetUpURLList to make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' Process each element in the list of web addresses.  
        For Each url In urlList  
            ' GetAsync returns a Task(Of HttpResponseMessage).   
            ' Argument ct carries the message if the Cancel button is chosen.   
            ' Note that the Cancel button can cancel all remaining downloads.  
            Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
            ' Retrieve the website contents from the HttpResponseMessage.  
            Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        Next  
    End Function  
  
    ' Add a method that creates a list of web addresses.  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
End Class  
  
' Sample output:  
  
' Length of the downloaded string: 35990.  
  
' Length of the downloaded string: 407399.  
  
' Length of the downloaded string: 226091.  
  
' Downloads canceled.  
```  
  
## <a name="see-also"></a>참고 항목  
 [Async 및 Await를 사용한 비동기 프로그래밍(Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)  
 [연습: Async 및 Await를 사용하여 웹에 액세스(Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 [비동기 작업 또는 작업 (Visual Basic) 목록 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)  
 [Async 응용 프로그램 미세 조정(Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)  
 [Async 샘플: 응용 프로그램 미세 조정](http://go.microsoft.com/fwlink/?LinkId=255046)

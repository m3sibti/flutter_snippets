# Alert Dialogs

## Info 
Currently this repository have following **Alert Dialog** examples:
<!-- TOC -->
 - [Simple Alert Dialog](#simple-alert-dialog)
 - [Alert Dialogs with TextField (Phone#)](#alert-dialog-with-textfield)
 <!-- /TOC -->
## Examples

 ### Simple Alert Dialog

    void myDialog(BuildContext ctx){
        final _title = Text('Authentication');
        final _content = Text('Please verify your phone number');
        final _actionTexts = [
          Text('Cancel'),
          Text('Verify'),
        ];
        _closeNavigator() {
          Navigator.of(ctx).pop();
        }
        _verifyPhoneNum() {
          print('Phone Number Verification');
          Navigator.of(ctx).pop();
        }
        final _cActions = [
          CupertinoDialogAction(
            child: _actionTexts[0],
            onPressed: () => _closeNavigator(),
          ),
          CupertinoDialogAction(
            child: _actionTexts[1],
            onPressed: () => _verifyPhoneNum(),
          ),
        ];
        final _aActions = [
          FlatButton(
            child: _actionTexts[0],
            onPressed: () => _closeNavigator(),
          ),
          FlatButton(
            child: _actionTexts[1],
            onPressed: () => _verifyPhoneNum(),
          ),
        ];
    
        var dialog = Platform.isIOS
            ? CupertinoAlertDialog(
                title: _title,
                content: _content,
                actions: _cActions,
              )
            : AlertDialog(
                title: _title,
                content: _content,
                actions: _aActions,
                elevation: 24,
              );
        showDialog(context: ctx, builder: (_) => dialog);
    }
***
 ### Alert Dialog With TextField

     void _phoneNumberSignIn(BuildContext ctx) {
        final _pNoController = TextEditingController();
        final _title = Text('Authentication');
        final _content = Column(
          mainAxisAlignment: MainAxisAlignment.center,
          crossAxisAlignment: CrossAxisAlignment.start,
          mainAxisSize: MainAxisSize.min,
          children: [
            Text('Please verify your phone number'),
            Container(
              padding: EdgeInsets.fromLTRB(0, 12, 0, 0),
              child: TextField(
                controller: _pNoController,
                keyboardType: TextInputType.phone,
                decoration: InputDecoration(
                  border: OutlineInputBorder(),
                  hintText: '+xxxxxxxxxxxx',
                ),
              ),
            ),
          ],
        );
        final _actionTexts = [
          Text('Cancel'),
          Text('Verify'),
        ];
        _closeNavigator() {
          Navigator.of(ctx).pop();
        }
    
        _verifyPhoneNum() {
          print('Phone Number = ${_pNoController.text}');
          Navigator.of(ctx).pop();
        }
    
        final _cActions = [
          CupertinoDialogAction(
            child: _actionTexts[0],
            onPressed: () => _closeNavigator(),
          ),
          CupertinoDialogAction(
            child: _actionTexts[1],
            onPressed: () => _verifyPhoneNum(),
          ),
        ];
        final _aActions = [
          FlatButton(
            child: _actionTexts[0],
            onPressed: () => _closeNavigator(),
          ),
          FlatButton(
            child: _actionTexts[1],
            onPressed: () => _verifyPhoneNum(),
          ),
        ];
    
        var dialog = Platform.isIOS
            ? CupertinoAlertDialog(
                title: _title,
                content: _content,
                actions: _cActions,
              )
            : AlertDialog(
                title: _title,
                content: _content,
                actions: _aActions,
                elevation: 24,
              );
        showDialog(context: ctx, builder: (_) => dialog);
      }
      
***
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTIzNjY2OTk5NCwzOTkwNjA1MzAsMTc0Mj
kxNTUyNF19
-->
# Alert Dialogs

## Info 
Currently this repository have following **Alert Dialog** examples:

<!-- TOC -->
 1. [Markdown Navigation](#markdown-navigation)
    - [Features](#features)
    - [Installation](#installation)
    - [Usage](#usage)
    - [What's New?](#whats-new)
    - [Question](#question)
    - [License](#license)
    - [Links](#links-e)
<!-- /TOC -->

 2. Simple Alert Dialog
 3. Alert Dialogs with TextField (Phone#)
 
## Examples

 ### Simpl

 4. List item

e Alert Dialog

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

 ### 2. Alert Dialog With TextField

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
### **3.  Links E
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1MjU1NTk1MzYsMzk5MDYwNTMwLDE3ND
I5MTU1MjRdfQ==
-->
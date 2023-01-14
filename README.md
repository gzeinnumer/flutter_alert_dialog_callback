# flutter_alert_dialog_callback

|<img src="/preview/preview1.png" width="300"/>|<img src="/preview/preview2.png" width="300"/>|<img src="/preview/preview3.png" width="300"/>|
|--|--|--|

```dart
showDialog(
  context: context,
  builder: (context) => ExamplesDialog(),
).then((value) {
  ScaffoldMessenger.of(context).showSnackBar(SnackBar(
    content: Text(value),
  ));
});
```

```dart
class ExamplesDialog extends StatelessWidget {
  final _editTextController = TextEditingController();
  ExamplesDialog({
    Key? key,
  }) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return AlertDialog(
      title: const Text('Are you sure?'),
      content: Wrap(
        children: [
          TextFormField(
            controller: _editTextController,
            decoration: const InputDecoration(hintText: "Hint"),
          )
        ],
      ),
      actions: <Widget>[
        TextButton(
          onPressed: () => Navigator.of(context).pop('NO'),
          child: const Text('NO'),
        ),
        TextButton(
          onPressed: () => Navigator.of(context).pop(_editTextController.text),
          child: const Text('YES'),
        )
      ],
    );
  }
}

```

---

```
Copyright 2023 M. Fadli Zein
```
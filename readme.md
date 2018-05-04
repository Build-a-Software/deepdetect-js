# deepdetect-js

> DeepDetect JS client

## Installation

```sh
npm install --save deepdetect-js
```

## Usage

```js
import DD from 'deepdetect-js';

async () => {

  const dd = new DD()

  // Get DeepDetect server info
  const info = await dd.info()
  console.log(info);

  // Create a service
  const serviceName = 'myserv';
  const serviceDescription = 'example classification service';
  const serviceMlLib = 'caffe';
  const serviceRepository = '/home/me/models/example';

  const createService = await dd.putService(
    serviceName,
    { repository: serviceRepository },
    serviceDescription,
    serviceMlLib,
    { connector: 'csv' },
    { nclasses: 9, layers: [512, 512, 512], activation: 'prelu' }
  );

  const service = await dd.getService(serviceName);
  console.log(service);

  const deleteService = await dd.deleteService(serviceName);

}
```

## Contributors

Thanks goes to these people ([emoji key](https://github.com/kentcdodds/all-contributors#emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
| [<img src="https://avatars2.githubusercontent.com/u/22868432?v=3" width="100px;"/><br /><sub>Alexandre Girard</sub>](https://github.com/alx)<br />[💻](https://github.com/alx/deepdetect-js/commits?author=alx "Code") [📖](https://github.com/alx/deepdetect-js/commits?author=alx "Documentation") [🚇](#infra-luftywiranda13 "Infrastructure (Hosting, Build-Tools, etc)") |
| :---: |
<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/kentcdodds/all-contributors) specification. Contributions of any kind welcome!

## License

MIT &copy; [Alexandre Girard](http://deepdetect.com)

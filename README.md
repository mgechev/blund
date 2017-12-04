<p align="center">
  <img width="460" height="300" src="/assets/sandman.jpeg">
</p>
<br>

# John Blund 😴

Sleep function. Convenient for unit testing and general purpose usage.

# Why "John Blund"?

That's the Swedish translation of the Western and North European folklore character Sandman who puts people to sleep.

# How to use?

```
npm i blund --save-dev
```

```ts
import sleep from 'blund';

class Service {
  foo(promise) {
    promise.then(() => this.bar());
  }

  bar(data) {
    // do stuff
  }
}

describe('async module', () => {
  let service;

  beforeEach(() => {
    service = new Service();
  });

  it('should work', async () => {
    const spy = spyOn(service, 'bar');
    service.foo(new Promise(resolve => setTimeout(resolve, 3)));

    await sleep(5);

    expect(spy).toHaveBeenCalled();
  });
});
```

# License

MIT


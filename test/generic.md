# TEST

## Compare objects

```
describe('Get Gifs', ()=> {
    test('Should return an array of gifs', ()=> {
        const gifs = await getGifs('smile');
        expect(gifs.length).toBeGreaterThan(0);
        expect(gifs[0]).toEqual({
            id: expect.any(String),
            title: expect.any(String),
            url: expect.any(String)
        })
    })
})
```

[<- Atras](../README.md)

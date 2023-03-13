# Glady frontend challenge

This project is a technical assesment

## Test

To see the component in action, first install it with this command (from this directory) :

```sh
npm install file://./calculator/dist/calculator
```

then go into the `tester` folder and run it with Angular CLI :

```sh
cd tester
ng serve
```

It will then be available on port 4200.

The [server](https://gitlab.com/wedoogift-jobs/challenge/-/tree/master/frontend/calculator-server) should be running if you want to see the full behavior

## Considerations

I made some design decisions with the limited available context, so here are some things that went through my mind during the process and I think might be relevant

### Design

Font can be set in the parent project at the global level, that's why it is not set.  
I wasn't sure about buttons, and it was quite ugly with default style so I choose to style them, but I could imagine a world where you would give them a class like `glady-default-button` and style this class in the global stylesheet.

### Service

I used an HttpClient directly because the component is simple, isolated (as far as I know at least) and HttpClient can be easily mocked for testing purposes. However, it multiple components used the same API I think it would make sense to have a service for this API that can be independently tested.

### Testing

Some tests are missing, it got really boring and it's getting late as I'm finishing this so I figured that since I showed many different examples it would be enough. The popup sub-component isn't tested for the same reason, but probably should be if it was a real project.

### Error messages

Although it wasn't asked for in the spec, I added error messages for connection errors and when the amount reaches the minimum or maximum values possible. I thought is was a bad idea to just silently fail, leaving the user wondering if something is broken or not. Again, not a real project, but if it was, that's probably something that I would have discussed in the design phase before starting developments.

## Authentication

If the component is to be used in a bigger application, with propably other calls made to the same API with the same authentication method, having an HttpInterceptor handle the authentication for all the app is propably a better choice than passing a token directly to each component

## Conclusion

I hope you'll be satisfied with the result, I'd be happy to discuss it further.  
In the meantime, you can check my personnal travel blog project on [github](https://github.com/morysh/frogginaround) and see the [result](https://frogginaround.com/).

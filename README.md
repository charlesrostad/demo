# Copy and paste the following to ad behaviour to the demo-dummy:


    hoodie.store.on('add:task', function(object) {
      $('.taskList').append('<li>'+object.desc+'</li>');
    });

    $('.addTask .submit').click(function(event){
        event.preventDefault();
        var desc = $('.addTask .desc').val();
        hoodie.store.add('task', {desc: desc});
    });

    $('.signUp .submit').click(function(event){
        event.preventDefault();
        var username = $('.signUp .username').val();
        var password = $('.signUp .password').val();
        hoodie.account.signUp(username, password).done(function(object){
            $('#hoodieAccountModal').modal('hide');
            $('.welcome').text('Hello, '+hoodie.account.username);
        });
    });

    $('.signIn .submit').click(function(event){
        event.preventDefault();
        var username = $('.signIn .username').val();
        var password = $('.signIn .password').val();
        hoodie.account.signIn(username, password).done(function(object){
            $('#hoodieAccountModal').modal('hide');
            $('.welcome').text('Hello, '+hoodie.account.username);
        });
    });



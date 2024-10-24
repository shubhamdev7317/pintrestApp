-- login and register screen
-- /register
-- /login
-- /profile - profile page with board
-- /feed - feed page with all different pins
-- /save/:pinid - save karega pin ko kisi board me 
-- /delete/:pinid - delete karega pin ko kisi board se
-- /logout
-- /edit
-- /upload


// for log out 
app.get('/logout', function(req, res, next){
  req.logout(function(err){
    if(err){
      return next(err);
    }
    res.redirect('/');
  })
})

function isLoggedIn(req, res, next){
  if(req.isAuthentticated()){
    return next();
  }
  res.redirect("/");
}
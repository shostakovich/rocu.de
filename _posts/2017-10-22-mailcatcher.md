---
layout: default
status: publish
published: true
title: "Rails: Preview your emails with MailCatcher"
abstract: Working with emails in Rails is quite comfortable if you are using the right tools.
image: /assets/images/2017-10/mailcatcher-preview.png
---

Do you know the feeling of copy and pasting the signup-link from this `development.log`? Theres a better way to do this.

For our development environment we use Mailcatcher.

![MailCatcher](/assets/images/2017-10/mailcatcher-preview.png)

> MailCatcher runs a super simple SMTP server which catches any message sent to it to display in a web interface. Run mailcatcher, set your favourite app to deliver to smtp://127.0.0.1:1025 instead of your default SMTP server, then check out http://127.0.0.1:1080 to see the mail that's arrived so far.

In this blogpost I show you how we set it up in our projects.

Mailcatcher is an awesome way to preview all the mails your Rails App sends in the developent environment. In this blog post I show you how you can set it up.

## Installation

Add MailCatcher and Foreman to your `Gemfile` :

{% highlight ruby %}
group :development do
  gem 'mailcatcher'
  gem 'foreman'
end
{% endhighlight %}

Run `bundle install`.

Create a file named `Procfile`. This is used to start Rails and MailCatcher together with one simple command.

```
web: rails s
mail: mailcatcher -f
```

The last step is to configure Rails to send emails to MailCatcher:

Add these 2 lines to your `config/environments/development.rb`.

{% highlight ruby %}
config.action_mailer.delivery_method = :smtp
config.action_mailer.smtp_settings = { address: 'localhost', port: 1025 }
{% endhighlight %}

Now you can run `foreman start` every time you want to start Rails.

This will start Rails and MailCatcher (which listens on port `1080`).

## Using Mailcatcher

![Mailcatcher](/assets/images/2017-10/mailcatcher.png)

Every time Rails sends an email MailCatcher will receive it and display it on at [http://localhost:1080/](http://localhost:1080/).


You can toggle between the HTML and the text portion of the email and even inspect the source.

## And what if I do not use Rails?

Well good news for you. You can also use MailCatcher.

1. Just install MailCatcher via `gem install mailcatcher`
2. Point your application to send mails via SMTP to port `1025`.
3. Run `mailcatcher`.
4. Go to [http://localhost:1080/](http://localhost:1080/).

## Conclusion

MailCatcher is one of these tools that we end up using whenever we start to send emails in a new project. I hope you like it as well.
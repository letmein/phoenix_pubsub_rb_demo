# frozen_string_literal: true
require 'rubygems'
require 'bundler'
Bundler.require(:default)

require 'phoenix/pubsub'

task default: %w[publish]

task :publish do
  p = Phoenix::Pubsub::Redis.new(redis_url: 'redis://localhost:6379', phoenix_class: 'Demo.PubSub')
  p.publish 'demo:feed', 'new:msg', { user: 'rake', body: 'hello from ruby!' }
end

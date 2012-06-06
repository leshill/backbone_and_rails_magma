!SLIDE commandline
# Generate your app

!SLIDE
# Generate a Rails controller to serve up our root page

    class BackboneController < ApplicationController
      private

      def items
        ... generates items
      end
      helper_method :items
    end

    BackboneAndRails::Application.routes.draw do
      root :to => 'backbone#index'
    end

    %h1 Welcome to the Backbone And Rails Example

    %ul
      - items.each do |item|
        %li
          %dl
            %dd Name
            %dt= item.name
            %dd Price
            %dt= item.price

!SLIDE
# Show a catalog the old school way
